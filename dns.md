<!-- # [ zrfisaac ] -->

<!-- # [ about ] -->
<!-- # - author : Isaac Caires -->
<!-- # . - email : zrfisaac@gmail.com -->
<!-- # . - site : zrfisaac.github.io -->
<!-- # - version : zrfisaac.wiki.pt.base : 0.0.1 -->

<!-- # [ markdown ] -->
# DNS

## Descrição
DNS é a sigla para **Domain Name System**, ou **Sistema de Nomes de Domínio**, em português. Ele funciona como uma espécie de "agenda telefônica" da internet.

Sempre que você digita o endereço de um site no navegador, como `www.google.com`, o DNS é o responsável por **traduzir esse nome em um endereço IP** (como `142.250.217.68`), que é o número que identifica o servidor onde o site está hospedado.

Em vez de você precisar decorar números IP, o DNS permite que você use nomes fáceis de lembrar. Esse processo de conversão é chamado de **resolução de nomes**.

---

## Índice
- [Ajuda](#ajuda)
  - [Servidor](#ajuda--servidor)
- IP
  - [Corel](#ip--corel)
  - [EA Games](#ip--ea-games)
  - [Microsoft](#ip--microsoft)
  - [Microsoft AD](#ip--microsoft-ad)

---

## [Ajuda](#índice)

### [Ajuda](#ajuda) > [Servidor](#índice)

| Provedor                | DNS Primário         | DNS Secundário       | Observações                           |
| ----------------------- | -------------------- | -------------------- | ------------------------------------- |
| **Google DNS**          | 8.8.8.8              | 8.8.4.4              | Muito usado, confiável                |
| **Cloudflare DNS**      | 1.1.1.1              | 1.0.0.1              | Foco em privacidade e velocidade      |
| **OpenDNS (Cisco)**     | 208.67.222.222       | 208.67.220.220       | Oferece filtro de conteúdo opcional   |
| **Quad9**               | 9.9.9.9              | 149.112.112.112      | Foco em segurança (bloqueia malwares) |
| **CleanBrowsing**       | 185.228.168.9        | 185.228.169.9        | Filtros para uso familiar e seguro    |
| **Comodo Secure DNS**   | 8.26.56.26           | 8.20.247.20          | Focado em segurança                   |
| **Google DNS IPv6**     | 2001:4860:4860::8888 | 2001:4860:4860::8844 | Endereços IPv6                        |
| **Cloudflare IPv6 DNS** | 2606:4700:4700::1111 | 2606:4700:4700::1001 | Endereços IPv6                        |

## [IP](#índice)

### [IP](#ip) > [Corel](#índice)

```
# Corel
127.0.0.1 apps.corel.com
127.0.0.1 origin-mgmt.corel.com
127.0.0.1 mc.corel.com
127.0.0.1 iws.corel.com
127.0.0.1 product.corel.com
127.0.0.1 corel.com
127.0.0.1 www.corel.com
127.0.0.1 activation.corel.com
127.0.0.1 register.corel.com
127.0.0.1 registration.corel.com
127.0.0.1 corel.pure.channel.lithium.com
127.0.0.1 discovery.corel.com
127.0.0.1 update.corel.com
127.0.0.1 download.corel.com
127.0.0.1 store1.corel.com
127.0.0.1 content.corel.com
127.0.0.1 origin.corel.com
127.0.0.1 origin-update.corel.com
127.0.0.1 origin-core.corel.com
127.0.0.1 winzip.com
127.0.0.1 www.winzip.com
127.0.0.1 activation.winzip.com
127.0.0.1 updates.winzip.com
127.0.0.1 register.winzip.com
127.0.0.1 registry.winzip.com
127.0.0.1 feedback.winzip.com
```

### [IP](#ip) > [EA Games](#índice)

```
# Corel
127.0.0.1 easo.ea.com
127.0.0.1 easports.com
127.0.0.1 www.ea.com
127.0.0.1 accounts.ea.com
127.0.0.1 cdn.accounts.ea.com
127.0.0.1 store.origin.com
127.0.0.1 api1.origin.com
127.0.0.1 api2.origin.com
127.0.0.1 origin.com
127.0.0.1 www.origin.com
127.0.0.1 origin-a.akamaihd.net
127.0.0.1 bltcdn.origin.ea.com
127.0.0.1 telemetry.origin.com
127.0.0.1 telemetry.ea.com
127.0.0.1 watson.telemetry.ea.com
127.0.0.1 cdp.origin.com
127.0.0.1 api.ea.com
127.0.0.1 image.ea.com
127.0.0.1 gamedata.ea.com
127.0.0.1 friends.easports.com
127.0.0.1 web.dm.origin.com
127.0.0.1 help.ea.com
127.0.0.1 connectivity.ea.com
127.0.0.1 emea.origin.com
127.0.0.1 api.sporigin.origin.com
127.0.0.1 sparta-easervices.ea.com
127.0.0.1 launcher.ea.com
127.0.0.1 accountsapi.ea.com
127.0.0.1 auth.api.ea.com
127.0.0.1 assets.ea.com
127.0.0.1 live-eaorigin.com
127.0.0.1 mt.ea.com
```

### [IP](#ip) > [Microsoft](#índice)

```
# Microsoft
127.0.0.1 windowsupdate.microsoft.com
127.0.0.1 update.microsoft.com
127.0.0.1 download.windowsupdate.com
127.0.0.1 dl.delivery.mp.microsoft.com
127.0.0.1 fe2.update.microsoft.com
127.0.0.1 fe3.delivery.mp.microsoft.com
127.0.0.1 tlu.dl.delivery.mp.microsoft.com
127.0.0.1 sls.update.microsoft.com
127.0.0.1 activation.microsoft.com
127.0.0.1 definitionupdates.microsoft.com
127.0.0.1 mp.microsoft.com
127.0.0.1 spynet2.microsoft.com
127.0.0.1 wdcp.microsoft.com
127.0.0.1 vortex.data.microsoft.com
127.0.0.1 settings-win.data.microsoft.com
127.0.0.1 storeedgefd.dsx.mp.microsoft.com
127.0.0.1 displaycatalog.mp.microsoft.com
127.0.0.1 storecatalogrevocation.storequality.microsoft.com
```

### [IP](#ip) > [Microsoft AD](#índice)

```
# Microsoft AD
127.0.0.1 www.bing.com
127.0.0.1 bing.com
127.0.0.1 cn.bing.com
127.0.0.1 www.msn.com
127.0.0.1 msn.com
127.0.0.1 assets.msn.com
127.0.0.1 arc.msn.com
127.0.0.1 nexus.officeapps.live.com
127.0.0.1 ads.msn.com
127.0.0.1 az416426.vo.msecnd.net
127.0.0.1 fe2.update.microsoft.com.akadns.net
127.0.0.1 settings-win.data.microsoft.com
127.0.0.1 activity.windows.com
127.0.0.1 watson.telemetry.microsoft.com
127.0.0.1 watson.ppe.telemetry.microsoft.com
127.0.0.1 telemetry.microsoft.com
127.0.0.1 telemetry.appex.bing.net
127.0.0.1 telemetry.urs.microsoft.com
127.0.0.1 v10.vortex-win.data.microsoft.com
127.0.0.1 v20.vortex-win.data.microsoft.com
127.0.0.1 vortex.data.microsoft.com
127.0.0.1 ads.microsoft.com
127.0.0.1 ad.doubleclick.net
127.0.0.1 g.msn.com
127.0.0.1 s0.2mdn.net
127.0.0.1 www.go.microsoft.com
127.0.0.1 storeedgefd.dsx.mp.microsoft.com
127.0.0.1 browser.events.data.msn.com
127.0.0.1 config.edge.skype.com
127.0.0.1 edge.microsoft.com
127.0.0.1 client.wns.windows.com
127.0.0.1 a.ads1.msn.com
127.0.0.1 a.ads2.msn.com
```
