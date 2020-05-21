---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721706"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a>La sintassi "BEGIN TRUSTED CERTIFICAte" non è più supportata per i certificati radice in Linux

I certificati radice in Linux e in altri sistemi di tipo UNIX, ma non macOS, possono essere presentati in due formati: l' `BEGIN CERTIFICATE` intestazione PEM standard e l'intestazione PEM specifica di OpenSSL `BEGIN TRUSTED CERTIFICATE` . La seconda sintassi consente la configurazione aggiuntiva che ha causato problemi di compatibilità con la classe di .NET Core <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> . `BEGIN TRUSTED CERTIFICATE`il contenuto del certificato radice non viene più caricato dal motore a catena a partire da .NET Core 3,0.

#### <a name="change-description"></a>Descrizione modifica:

In precedenza, `BEGIN CERTIFICATE` `BEGIN TRUSTED CERTIFICATE` per popolare l'elenco di attendibilità radice venivano utilizzate entrambe le sintassi e. Se `BEGIN TRUSTED CERTIFICATE` è stata utilizzata la sintassi e sono state specificate opzioni aggiuntive nel file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> potrebbe essere stato segnalato che il trust della catena non è consentito in modo esplicito ( <xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType> ). Tuttavia, se il certificato è stato specificato anche con la `BEGIN CERTIFICATE` sintassi in un file caricato in precedenza, il trust a catena era consentito.

A partire da .NET Core 3,0, `BEGIN TRUSTED CERTIFICATE` i contenuti non vengono più letti. Se il certificato non viene specificato anche tramite una `BEGIN CERTIFICATE` sintassi standard, <xref:System.Security.Cryptography.X509Certificates.X509Chain> segnala che la radice non è attendibile ( <xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType> ).

#### <a name="version-introduced"></a>Versione introdotta

3.0

#### <a name="recommended-action"></a>Azione consigliata

La maggior parte delle applicazioni non è interessata da questa modifica, ma le applicazioni che non riescono a visualizzare entrambe le origini certificati radice a causa di problemi di autorizzazioni potrebbero riscontrare errori imprevisti `UntrustedRoot` dopo l'aggiornamento

Molte distribuzioni Linux (o distribuzioni) scrivono certificati radice in due posizioni: una directory con un certificato per file e una concatenazione di un file. In alcune distribuzioni, la directory con un certificato per file usa la `BEGIN TRUSTED CERTIFICATE` sintassi mentre la concatenazione dei file usa la `BEGIN CERTIFICATE` sintassi standard. Assicurarsi che tutti i certificati radice personalizzati vengano aggiunti come `BEGIN CERTIFICATE` in almeno uno di questi percorsi e che entrambe le posizioni possano essere lette dall'applicazione.

La directory tipica è */etc/ssl/certs/* e il file concatenato tipico è */etc/SSL/cert.pem*. Usare il comando `openssl version -d` per determinare la radice specifica della piattaforma, che può differire da */etc/SSL/*. Ad esempio, in Ubuntu 18,04, la directory è */usr/lib/SSL/certs/* e il file è */usr/lib/SSL/cert.pem*. Tuttavia, */usr/lib/SSL/certs/* è un collegamento simbolico a */etc/ssl/certs/* e */usr/lib/SSL/cert.pem* non esiste.

```bash
$ openssl version -d
OPENSSLDIR: "/usr/lib/ssl"
$ ls -al /usr/lib/ssl
total 12
drwxr-xr-x  3 root root 4096 Dec 12 17:10 .
drwxr-xr-x 73 root root 4096 Feb 20 15:18 ..
lrwxrwxrwx  1 root root   14 Mar 27  2018 certs -> /etc/ssl/certs
drwxr-xr-x  2 root root 4096 Dec 12 17:10 misc
lrwxrwxrwx  1 root root   20 Nov 12 16:58 openssl.cnf -> /etc/ssl/openssl.cnf
lrwxrwxrwx  1 root root   16 Mar 27  2018 private -> /etc/ssl/private
```

#### <a name="category"></a>Category

Crittografia

#### <a name="affected-apis"></a>API interessate

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
