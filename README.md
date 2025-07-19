
---

## 🛠️ Steps with Commands & Explanations

```bash
# 1. Create folder structure
mkdir -p ~/FUTURE_CS_03/{reports,screenshots,secure-files}
cd ~/FUTURE_CS_03/secure-files

# 2. Create a confidential file
nano secret_plan.txt
# Type your secret message and save with Ctrl + O, Enter, Ctrl + X

# 3. Encrypt the file
gpg -c secret_plan.txt
# Enter passphrase: future@123 → creates secret_plan.txt.gpg

# 4. Decrypt the file to test
gpg secret_plan.txt.gpg
# Enter the same passphrase to restore original file

# 5. Generate hash of original and decrypted file
sha256sum secret_plan.txt > original_hash.txt
sha256sum secret_plan.txt > decrypted_hash.txt

# 6. Compare the two hashes
diff original_hash.txt decrypted_hash.txt
# No output means both hashes match ✅

# 7. Take a screenshot as proof
gnome-screenshot -a
# Save as: screenshots/task3_encryption_demo.png
