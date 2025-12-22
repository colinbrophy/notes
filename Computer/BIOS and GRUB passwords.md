
**Summary:**  
BIOS and GRUB passwords offer some protection against physical tampering but are often unnecessary if you're using full disk encryption (FDE) and follow good security practices.

**When You Can Skip Them:**

- You use **full disk encryption** (e.g. LUKS).
- Your **bootloader and kernel are inside the encrypted volume**.
- You **lock your screen** when away.
- You **trust people with physical access** to your machine.
- You're **not worried about state actors or sophisticated tampering**.

**When They Might Matter:**

- You use **TPM-sealed auto-unlock** (BIOS password helps protect TPM config).
- You often **travel with your device** (adds a layer if stolen).
- You **share access** with less trusted users (prevents boot option tampering).
- You want **defence in depth**.

**Conclusion:**  
If your system is encrypted and properly locked, BIOS and GRUB passwords are generally unnecessary for day-to-day personal security. They're mainly useful in high-risk or multi-user scenarios.