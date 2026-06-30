#!/bin/bash \
&& set -e

TARGET="https://petstore.swagger.io" \
&& OUTPUT="api_recon.txt"

echo "[+] Installing dependencies..." | tee $OUTPUT \
&& pip3 install --quiet arjun httpx jq requests

echo -e "\n[+] Fetching Swagger JSON..." | tee -a $OUTPUT \
&& curl -s https://petstore.swagger.io/v2/swagger.json -o swagger.json

echo -e "\n[+] Extracting API Routes..." | tee -a $OUTPUT \
&& jq -r '.paths | keys[]' swagger.json | tee -a $OUTPUT > routes.txt

echo -e "\n[+] Enumerating API Structure..." | tee -a $OUTPUT \
&& jq '.paths' swagger.json | tee -a $OUTPUT

echo -e "\n[+] Running Arjun (GET parameter discovery)..." | tee -a $OUTPUT \
&& arjun -i routes.txt -m GET -oT arjun_params.txt \
&& cat arjun_params.txt | tee -a $OUTPUT

echo -e "\n[+] API Recon Complete. Results saved to $OUTPUT"
