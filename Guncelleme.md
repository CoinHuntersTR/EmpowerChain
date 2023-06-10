## Zincir versiyonunu güncelliyoruz
[BURADAN](https://discord.com/channels/948213834164883488/1039946934040936508/1116723754949677167) Discord duyursunu kontrol edebilirsiniz.

#  v1.0.0-rc2 Güncellemesi

```
cd empowerchain
```
```
git pull
```
```
cd chain
```
```
git checkout v1.0.0-rc2
```
```
make install
```

* Güncelleme tamamlandıktan sonra Empowerchain versiyonu kontrol ediyoruz.
```
empowerd version
```

# Node tekrar başlatıyoruz. 
```
sudo systemctl restart empowerd && journalctl -u empowerd -f --no-hostname -o cat
```
