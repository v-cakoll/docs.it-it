---
ms.openlocfilehash: 3c6142fd536bad5676f02570fecd4eb0605db829
ms.sourcegitcommit: 0926684d8d34f4c6b5acce58d2193db093cb9cf2
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/20/2020
ms.locfileid: "83721706"
---
### <a name="begin-trusted-certificate-syntax-no-longer-supported-for-root-certificates-on-linux"></a><span data-ttu-id="c473a-101">La sintassi "BEGIN TRUSTED CERTIFICAte" non è più supportata per i certificati radice in Linux</span><span class="sxs-lookup"><span data-stu-id="c473a-101">"BEGIN TRUSTED CERTIFICATE" syntax no longer supported for root certificates on Linux</span></span>

<span data-ttu-id="c473a-102">I certificati radice in Linux e in altri sistemi di tipo UNIX, ma non macOS, possono essere presentati in due formati: l' `BEGIN CERTIFICATE` intestazione PEM standard e l'intestazione PEM specifica di OpenSSL `BEGIN TRUSTED CERTIFICATE` .</span><span class="sxs-lookup"><span data-stu-id="c473a-102">Root certificates on Linux and other Unix-like systems (but not macOS) can be presented in two forms: the standard `BEGIN CERTIFICATE` PEM header, and the OpenSSL-specific `BEGIN TRUSTED CERTIFICATE` PEM header.</span></span> <span data-ttu-id="c473a-103">La seconda sintassi consente la configurazione aggiuntiva che ha causato problemi di compatibilità con la classe di .NET Core <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> .</span><span class="sxs-lookup"><span data-stu-id="c473a-103">The latter syntax allows for additional configuration that has caused compatibility issues with .NET Core's <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName> class.</span></span> <span data-ttu-id="c473a-104">`BEGIN TRUSTED CERTIFICATE`il contenuto del certificato radice non viene più caricato dal motore a catena a partire da .NET Core 3,0.</span><span class="sxs-lookup"><span data-stu-id="c473a-104">`BEGIN TRUSTED CERTIFICATE` root certificate contents are no longer loaded by the chain engine starting in .NET Core 3.0.</span></span>

#### <a name="change-description"></a><span data-ttu-id="c473a-105">Descrizione modifica:</span><span class="sxs-lookup"><span data-stu-id="c473a-105">Change description</span></span>

<span data-ttu-id="c473a-106">In precedenza, `BEGIN CERTIFICATE` `BEGIN TRUSTED CERTIFICATE` per popolare l'elenco di attendibilità radice venivano utilizzate entrambe le sintassi e.</span><span class="sxs-lookup"><span data-stu-id="c473a-106">Previously, both the `BEGIN CERTIFICATE` and `BEGIN TRUSTED CERTIFICATE` syntaxes were used to populate the root trust list.</span></span> <span data-ttu-id="c473a-107">Se `BEGIN TRUSTED CERTIFICATE` è stata utilizzata la sintassi e sono state specificate opzioni aggiuntive nel file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> potrebbe essere stato segnalato che il trust della catena non è consentito in modo esplicito ( <xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="c473a-107">If the `BEGIN TRUSTED CERTIFICATE` syntax was used and additional options were specified in the file, <xref:System.Security.Cryptography.X509Certificates.X509Chain> may have reported that the chain trust was explicitly disallowed (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.ExplicitDistrust?displayProperty=nameWithType>).</span></span> <span data-ttu-id="c473a-108">Tuttavia, se il certificato è stato specificato anche con la `BEGIN CERTIFICATE` sintassi in un file caricato in precedenza, il trust a catena era consentito.</span><span class="sxs-lookup"><span data-stu-id="c473a-108">However, if the certificate was also specified with the `BEGIN CERTIFICATE` syntax in a previously loaded file, the chain trust was allowed.</span></span>

<span data-ttu-id="c473a-109">A partire da .NET Core 3,0, `BEGIN TRUSTED CERTIFICATE` i contenuti non vengono più letti.</span><span class="sxs-lookup"><span data-stu-id="c473a-109">Starting in .NET Core 3.0, `BEGIN TRUSTED CERTIFICATE` contents are no longer read.</span></span> <span data-ttu-id="c473a-110">Se il certificato non viene specificato anche tramite una `BEGIN CERTIFICATE` sintassi standard, <xref:System.Security.Cryptography.X509Certificates.X509Chain> segnala che la radice non è attendibile ( <xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType> ).</span><span class="sxs-lookup"><span data-stu-id="c473a-110">If the certificate is not also specified via a standard `BEGIN CERTIFICATE` syntax, the <xref:System.Security.Cryptography.X509Certificates.X509Chain> reports that the root is not trusted (<xref:System.Security.Cryptography.X509Certificates.X509ChainStatusFlags.UntrustedRoot?displayProperty=nameWithType>).</span></span>

#### <a name="version-introduced"></a><span data-ttu-id="c473a-111">Versione introdotta</span><span class="sxs-lookup"><span data-stu-id="c473a-111">Version introduced</span></span>

<span data-ttu-id="c473a-112">3.0</span><span class="sxs-lookup"><span data-stu-id="c473a-112">3.0</span></span>

#### <a name="recommended-action"></a><span data-ttu-id="c473a-113">Azione consigliata</span><span class="sxs-lookup"><span data-stu-id="c473a-113">Recommended action</span></span>

<span data-ttu-id="c473a-114">La maggior parte delle applicazioni non è interessata da questa modifica, ma le applicazioni che non riescono a visualizzare entrambe le origini certificati radice a causa di problemi di autorizzazioni potrebbero riscontrare errori imprevisti `UntrustedRoot` dopo l'aggiornamento</span><span class="sxs-lookup"><span data-stu-id="c473a-114">Most applications are unaffected by this change, but applications that cannot see both root certificate sources because of permissions problems may experience unexpected `UntrustedRoot` errors after upgrading.</span></span>

<span data-ttu-id="c473a-115">Molte distribuzioni Linux (o distribuzioni) scrivono certificati radice in due posizioni: una directory con un certificato per file e una concatenazione di un file.</span><span class="sxs-lookup"><span data-stu-id="c473a-115">Many Linux distributions (or distros) write root certificates into two locations: a one-certificate-per-file directory, and a one-file concatenation.</span></span> <span data-ttu-id="c473a-116">In alcune distribuzioni, la directory con un certificato per file usa la `BEGIN TRUSTED CERTIFICATE` sintassi mentre la concatenazione dei file usa la `BEGIN CERTIFICATE` sintassi standard.</span><span class="sxs-lookup"><span data-stu-id="c473a-116">On some distros, the one-certificate-per-file directory uses the `BEGIN TRUSTED CERTIFICATE` syntax while the file concatenation uses the standard `BEGIN CERTIFICATE` syntax.</span></span> <span data-ttu-id="c473a-117">Assicurarsi che tutti i certificati radice personalizzati vengano aggiunti come `BEGIN CERTIFICATE` in almeno uno di questi percorsi e che entrambe le posizioni possano essere lette dall'applicazione.</span><span class="sxs-lookup"><span data-stu-id="c473a-117">Ensure that any custom root certificates are added as `BEGIN CERTIFICATE` in at least one of these locations, and that both locations can be read by your application.</span></span>

<span data-ttu-id="c473a-118">La directory tipica è */etc/ssl/certs/* e il file concatenato tipico è */etc/SSL/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="c473a-118">The typical directory is */etc/ssl/certs/* and the typical concatenated file is */etc/ssl/cert.pem*.</span></span> <span data-ttu-id="c473a-119">Usare il comando `openssl version -d` per determinare la radice specifica della piattaforma, che può differire da */etc/SSL/*.</span><span class="sxs-lookup"><span data-stu-id="c473a-119">Use the command `openssl version -d` to determine the platform-specific root, which may differ from */etc/ssl/*.</span></span> <span data-ttu-id="c473a-120">Ad esempio, in Ubuntu 18,04, la directory è */usr/lib/SSL/certs/* e il file è */usr/lib/SSL/cert.pem*.</span><span class="sxs-lookup"><span data-stu-id="c473a-120">For example, on Ubuntu 18.04, the directory is */usr/lib/ssl/certs/* and the file is */usr/lib/ssl/cert.pem*.</span></span> <span data-ttu-id="c473a-121">Tuttavia, */usr/lib/SSL/certs/* è un collegamento simbolico a */etc/ssl/certs/* e */usr/lib/SSL/cert.pem* non esiste.</span><span class="sxs-lookup"><span data-stu-id="c473a-121">However, */usr/lib/ssl/certs/* is a symlink to */etc/ssl/certs/* and */usr/lib/ssl/cert.pem* does not exist.</span></span>

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

#### <a name="category"></a><span data-ttu-id="c473a-122">Category</span><span class="sxs-lookup"><span data-stu-id="c473a-122">Category</span></span>

<span data-ttu-id="c473a-123">Crittografia</span><span class="sxs-lookup"><span data-stu-id="c473a-123">Cryptography</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="c473a-124">API interessate</span><span class="sxs-lookup"><span data-stu-id="c473a-124">Affected APIs</span></span>

- <xref:System.Security.Cryptography.X509Certificates.X509Chain?displayProperty=fullName>

<!--

#### Affected APIs

- `T:System.Security.Cryptography.X509Certificates.X509Chain`

-->
