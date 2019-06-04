---
title: Esempio di FindPrivateKey - WCF
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: b89d135d7412f10cb9de1e4bda1aaab14b29cbf0
ms.sourcegitcommit: 155012a8a826ee8ab6aa49b1b3a3b532e7b7d9bd
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2019
ms.locfileid: "66490777"
---
# <a name="findprivatekey-sample"></a>Esempio FindPrivateKey

Può essere difficile individuare il percorso e il nome del file di chiave privata associati a un certificato X.509 specifico nell'archivio certificati. Lo strumento FindPrivateKey.exe facilita questo processo.

> [!IMPORTANT]
> FindPrivateKey è un esempio che deve essere compilato prima dell'utilizzo. Vedere le [per compilare il progetto FindPrivateKey](#to-build-the-findprivatekey-project) per istruzioni su come compilare lo strumento FindPrivateKey.

I certificati X.509 vengono installati da un amministratore o da qualsiasi utente nel computer. Tuttavia, il certificato sono accessibili da un servizio in esecuzione con un account diverso. Ad esempio, l'account del servizio di rete.

Questo account può non avere accesso al file di chiave privata se il certificato non è stato originariamente installato. Lo strumento FindPrivateKey fornisce il percorso del file di chiave privata di un determinato certificato X.509. È possibile aggiungere o rimuovere autorizzazioni quando si conosce il percorso del file di chiave privata degli specifici certificati X.509.

Gli esempi che usano certificati per la sicurezza utilizzano lo strumento FindPrivateKey nel *Setup. bat* file. Una volta individuato il file di chiave privata, è possibile usare altri strumenti, ad esempio *Cacls.exe* per impostare i diritti di accesso appropriati sul file.

Quando si esegue un servizio Windows Communication Foundation (WCF) con un account utente, ad esempio un file eseguibile indipendente, assicurarsi che l'account utente disponga di accesso in lettura al file. Quando si esegue un servizio WCF in Internet Information Services (IIS) gli account predefiniti quali viene eseguito il servizio sono il servizio di rete in IIS 7 e versioni precedenti, o identità Pool di applicazioni in IIS 7.5 e versioni successive. Per altre informazioni, vedere [Application Pool Identities](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Esempi

Quando si accede a un certificato per il quale il processo non dispone di privilegi di lettura, viene visualizzato un messaggio di eccezione simile all'esempio seguente:

```
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

In questo caso, utilizzare lo strumento FindPrivateKey per trovare il file di chiave privata e quindi impostare il diritto di accesso per il processo di cui è in esecuzione il servizio. Ad esempio, questa operazione può essere eseguita con lo strumento Cacls.exe come illustrato nell'esempio seguente:

```
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>Per compilare il progetto FindPrivateKey

Per scaricare il progetto, visitare [Windows Communication Foundation (WCF) e gli esempi di Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Aprire Esplora File e passare per il *WF_WCF_Samples\WCF\Setup\FindPrivateKey\CS* cartella nel percorso della directory in cui è installato l'esempio.

2. Fare doppio clic sull'icona del file con estensione sln per aprirlo in Visual Studio.

3. Nel **compilare** dal menu **Ricompila soluzione**.

4. La compilazione della soluzione genera il file: FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>Convenzioni: voci della riga di comando

 "[*opzione*]" rappresenta un set facoltativo di parametri.

 "{*opzione*}" rappresenta un set di parametri obbligatorio.

 "*opzione1* &#124; *opzione2*" rappresenta una scelta tra set di opzioni.

 "\<*valore*>" rappresenta un valore del parametro da immettere.

## <a name="usage"></a>Utilizzo

```
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

Dove:

```
       <subjectName> The subject name of the certificate
       <thumbprint>  The thumbprint of the certificate (You can use the Certmgr.exe tool to find this)
       -f            output file name only
       -d            output directory only
       -a            output absolute file name
```

Se viene specificato alcun parametro al prompt dei comandi, viene visualizzato il testo della Guida.

## <a name="examples"></a>Esempi

In questo esempio viene ricercato il nome file del certificato con un nome soggetto "CN = localhost", nell'archivio personale dell'utente corrente.

```
FindPrivateKey My CurrentUser -n "CN=localhost"
```

In questo esempio viene ricercato il nome file del certificato con un nome soggetto "CN = localhost", nel profilo personale archivio dell'utente corrente e il percorso completo della directory di output.

```
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

In questo esempio viene ricercato il nome del file del certificato con un'identificazione digitale di "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", nell'archivio Personale del computer locale.

```
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
