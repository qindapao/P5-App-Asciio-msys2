# P5-App-Asciio-msys2
[P5-App-Asciio](https://github.com/nkh/P5-App-Asciio) Windows AMD64(x86_64) `msys2` environment distribution package.

The installation package is relatively large because it contains the complete build tool chain.

Please go to `release` to download.

## How to use

**(1)**. Download the installation package and decompress it. Please use [7zip](https://www.7-zip.org/) to decompress it.

After installing `7zip`, remember to add its installation directory to the system environment variables. Then you can use the `7z` command to decompress in `powershell`, or you can use the `7zip` client.

```powershell
7z x .\msys64.zip
7z x .\msys64.7z
```

Note: It is recommended to decompress to a root directory.

**(2)**. Open the `ucrt64.exe` terminal in the installation package.

**(3)**. Replace the perl environment variable with your installation path (if you decompress it to the root directory of drive D, you can skip this step directly).

For example, if you decompress it to the root directory of drive C, you need to execute the following command in the `UCRT64` terminal:

```bash
cp /ucrt64/lib/perl5/core_perl/Config.pm /ucrt64/lib/perl5/core_perl/Config.bak
cp /ucrt64/lib/perl5/core_perl/Config_heavy.pl /ucrt64/lib/perl5/core_perl/Config_heavy.bak
sed -i.bak 's|D:\\\\msys64|C:\\\\msys64|g' /ucrt64/lib/perl5/core_perl/Config.pm
sed -i.bak 's|D:\\msys64|C:\\msys64|g' /ucrt64/lib/perl5/core_perl/Config_heavy.pl
```

Note: This step only needs to be done when starting the `UCRT64` terminal for the first time, and is not required later.

**(4)**. Run `asciio`.

---

Here is a small demonstration video:

![msys2_install_demo](msys2_install_demo.gif)


## How to choose the running mode

1. Seamlessly integrate with `Windows` workflow, `msys2` version is recommended.
2. If working under `Linux` or `WSL`, the native version of `Linux` is recommended.
3. If you want to deploy and use it quickly, the container version is recommended.

