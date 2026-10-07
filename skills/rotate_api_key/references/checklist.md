# Key rotation checklist

1. Create the new key with the provider.
2. Store it in the secrets manager under the same name, as a new version.
3. Restart or roll every service that reads it.
4. Confirm traffic succeeds with the new key.
5. Revoke the old key.
