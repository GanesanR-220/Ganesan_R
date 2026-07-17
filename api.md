#!/usr/bin/env bash

echo "=== Host Information ==="
hostname
uname -a

echo
echo "=== Current User ==="
whoami
id

echo
echo "=== Current User's Sudo Privileges ==="
sudo -l 2>/dev/null || echo "Unable to query sudo privileges."

echo
echo "=== Local Users ==="
getent passwd | cut -d: -f1

echo
echo "=== Local Groups ==="
getent group | cut -d: -f1

echo
echo "=== Group Memberships ==="
for u in $(getent passwd | cut -d: -f1); do
    printf "%-20s: " "$u"
    id -nG "$u"
done
