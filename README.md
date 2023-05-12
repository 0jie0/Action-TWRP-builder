# ʹ��Github Action������ָ�

- ֧��SHRP, TWRP �ı��������

---

## ��л
- ���й�����
- ĪĪ���� README.md
---

## OrangeFox is [here](https://github.com/azwhikaru/Action-OFRP-Builder)

## ����˵��
```
= 2022/10/28
- OFRP�嵥�ѱ��޸ģ��������ڲ���ȫ֧��OFRP��������ܽ��������⣬���ύһ��PR���󣡣���

= 2022/07/08
- TWRP�ͻ���TWRP��5.X ~ 12.X��***ȫ���ɹ������***��

= 2022/07/06
- Add support for 5.1 branch

= 2022/07/05
- Updated to work with trees back to 6.0
- Add conditionals to include common trees for syncing
- Update README for SSH keys

= 2022/07/04
- Updated to work with Android 12.1 AOSP minimal TWRP manifest

= 2022/05/29
- Should work correctly with Android 11 based source code

= 2022/02/03
- Due to the hardware resource limitation of GitHub action, this version cannot be compiled based on AOSP and other source codes of Android 11 and above. If necessary, please use local compilation

= 2021/10/29: 
- Refactored version 2.0
- Completely reconstruct the use logic to reduce the difficulty of use
- Optimize the parameter transfer part, now you can run multiple Workers at the same time
```

-----

## ��������

| ���� | ���� | ʾ�� |
| ------------ | -------------------- | ------------ |
| `MANIFEST_URL` | Դ���ַ | https://github.com/minimal-manifest-twrp/platform_manifest_twrp_aosp.git |
| `MANIFEST_BRANCH` | Դ���֧ | twrp-12.1 |
| `DEVICE_TREE_URL` | �豸����ַ | https://github.com/TeamWin/android_device_asus_I003D |
| `DEVICE_TREE_BRANCH` | �豸����֧ | android-12.1 |
| `DEVICE_PATH` | �豸λ�� | device/asus/I003D |
| `COMMON_TREE_URL` | ͨ���豸����ַ��û�еĻ�������д�� | https://github.com/TeamWin/android_device_asus_sm8250-common |
| `COMMON_PATH` | ͨ���豸��ַ��û�еĻ�������д�� | device/asus/sm8250-common |
| `DEVICE_NAME` | �������� | I003D |
| `MAKEFILE_NAME` | �����ļ��� | omni_I003D |
| `BUILD_TARGET` | ����Ŀ����� (boot/recovery/vendorboot) | recovery |

-----

## ����ʹ�ã�
```
���磬����û����ǣ�JohnSmith
```
#### 1. �������Դ�����Ͻǵ�'Fork'
![image](https://user-images.githubusercontent.com/37921907/177914706-c92476c5-7e14-4fb3-be94-0c8a11dae874.png)
#### 2. �ڵȴ��Զ��ض������ῴ�����Լ����û���
![image](https://user-images.githubusercontent.com/37921907/177915106-5bde6fc9-303c-479e-b290-22b48efd1e4e.png)
#### 3. �ı�[�û����͵����ʼ�](https://github.com/CaptainThrowback/Action-Recovery-Builder/blob/main/.github/workflows/Recovery%20Build.yml#L100-L101) �ڹ��������з�ӳ���Github֤�飨��ѡ��
## ����SSH��Կ����ѡ��
#### 4. �������ã�Ȼ��ѡ������Կ��ѡ�� "��Ӳ�����Կ "��ť��

#### 5. ����İ�׿�豸�ϣ���װ[Termux](https://github.com/termux/termux-app/releases)

#### 6. ��Termux�а�װopenssh������ssh��Կ��(��Ҫʹ����Կ�Ŀ���)
NOTE: When creating the deploy key for a repository like git@github.com:owner/repo.git or https://github.com/owner/repo, put that URL into the key comment. (Hint: Try ssh-keygen ... -C "git@github.com:owner/repo.git".)
owner = your Github username
```
pkg install openssh
ssh-keygen -t ed25519 -C "git@github.com:owner/Action-Recovery-Builder.git"
```
#### 7. ����Կ��ӵ���� repo �С���Termux�У�ʹ���������
```
cd /data/data/com.termux/files/usr/etc/ssh
cat ssh_host_ed25519_key.pub
```
  Select and copy the key then paste in the box for Key.
  You can name it whatever you choose for the title.

#### 8. ����Ҫ������˽��SSH��Կ���ص�Termux�С�
```
cat ssh_host_ed25519_key
```
   ����Termux�������

   �����������У�ѡ��ȫ��ǩ�µ�*����*��
   ѡ�� Actions
   ѡ�� New repository secret
   �����µ��������ƣ���Ӧ���� SSH_PRIVATE_KEY
   ��ssh_host_ed25519_key�����ճ����Value���С�
   Ȼ��ѡ�� Add secret.

## �����ָ�
#### 9. ��� 'Actions-Recovery Build'
![image](https://user-images.githubusercontent.com/37921907/177915304-8731ed80-1d49-48c9-9848-70d0ac8f2720.png)
#### 10. ��д��Ϻ󣬵�� "Run workflow�� ������������'��������'������д��
![image](https://user-images.githubusercontent.com/37921907/177915346-71c29149-78fb-4a00-996f-5d84ffc9eb8c.png)
#### 11. ��д��Ϻ󣬵�� "Run workflow "��ʼ���С�
-----

## ������
������������ַ���� [Release](../../releases)

-----
## ע��

#### TeamWin Recovery Project: https://github.com/minimal-manifest-twrp
#### OrangeFox Recovery Project: https://gitlab.com/OrangeFox
#### SKYHAWK Recovery Project: https://github.com/SHRP/platform_manifest_twrp_omni

![Alt](https://repobeats.axiom.co/api/embed/775def677c1ec4f2d739cc66d6d9d42687a41e02.svg "Repobeats analytics image")
