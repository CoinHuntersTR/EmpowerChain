# EmpowerChain
![image](https://docs.empowerchain.io/assets/empowerchain-banner.f628b327.png)

## Ödüllü Testnete Katılım
* Ödüllü Testnete katılmak için [BURADAN](https://docs.google.com/forms/d/e/1FAIpQLSe1kuSWQq_zaxeR9Fn2lx2VsF073pY2jgGNJHz4obPCF7yYGg/viewform) formu doldurmayı UNTUMAYIN!
* Empowerchain [DİSCORD](https://discord.gg/tf8WRDCBrj) kanalına katılalım.

## Kurulum Öncesi Notlar
### Testnet 3 aşamadan oluşuyor
* 31 Mayıs - 6 Haziran: Ağ önyükleme aşaması
* 7 Haziran - 20 Haziran: Ana aşama
* 21 Haziran - 25 Haziran: Stres testi aşaması
#### Ödüller 1 yıl lineer vestingli dağıtılacak!!

* Testnet sonunda KYC olacak
## Sistem gereksinimleri:
NODE TİPİ | CPU     | RAM      | SSD     |
| ------------- | ------------- | ------------- | -------- |
| Empower | 4          | 8        | 200  |
 

![hetzner](https://github.com/CoinHuntersTR/EmpowerChain/assets/111747226/46d2e1ea-0714-4061-b5a2-476be023cfd0)

* Hetzner için bu gereksinimleri almka yeterli olacaktır.
Hetzner kaydınız yok ise [BURADAN](https://hetzner.cloud/?ref=ew4WgPUfxeyJ) linke basıp 20€ değerinde ödül kazanıp, testnete katılabilirsiniz.

## Script ile kurulum;
```
curl -sSL -o empower-kurulum.sh https://raw.githubusercontent.com/CoinHuntersTR/EmpowerChain/main/empower-kurulum.sh && chmod +x empower-kurulum.sh && bash ./empower-kurulum.sh
```
* Tek bu kodu çalıştırmanız yeterli olacaktır.

## Kurulum tamamlandıktan sonra;
```
source $HOME/.bash_profile
```
## Logları Görüntüleme
```
 sudo journalctl -u empowerd -fo cat
```
![log-kaydi](https://github.com/CoinHuntersTR/EmpowerChain/assets/111747226/b92c90fb-7788-411b-a6f8-adc31e9884dc)


## Cüzdan Oluşturma;
```
empowerd keys add cüzdanadi
```
* "cüzdanadi" bölümüne istediğiniz bir isim verebilirsiniz.,
*  Cüzdanınızı oluşturduktan sonra size verilen gizli kelimelerinizi ve cüzdan adresinizi bir yere not etmeyi unutmayın.




## Önemli Notlar.
* Şuan Faucet yok bu nedenle bu bölümü faucet açıldıktan sonra yapacaksınız.
* Şuan node kurup sync olmayı bekliyoruz. Faucet açıldıktan sonra aşağıdaki bölüme devam edeceğiz.

## Validator Oluşturma;

* "cüzdanadi" yazan yere kendi cüzdanadınızı yazacaksınız.
* "twitter adresinizi ekleyebilirsiniz." yazan yere " kalacak şekilde twitter adresinizi ekleyebilirsiniz.
```
empowerd tx staking create-validator \
  --amount 1000000umpwr \
  --from cüzdanadi \
  --commission-max-change-rate "0.01" \
  --commission-max-rate "0.2" \
  --commission-rate "0.1" \
  --min-self-delegation "1" \
  --pubkey  $(empowerd tendermint show-validator) \
  --moniker $MONIKER \
  --website "twitter adresinizi ekleyebilirsiniz."
  --details "twitter adresinizi ekleyebilirsiniz" \
  --chain-id circulus-1
  --y
```
