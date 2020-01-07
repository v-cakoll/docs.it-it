---
title: Esempio FindPrivateKey
ms.date: 12/04/2017
helpviewer_keywords:
- FindPrivateKey
ms.assetid: 16b54116-0ceb-4413-af0c-753bb2a785a6
ms.openlocfilehash: 0ed1e5e81a5d2f7f3586e5dce306e8244b5ebd48
ms.sourcegitcommit: 30a558d23e3ac5a52071121a52c305c85fe15726
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/25/2019
ms.locfileid: "75346022"
---
# <a name="findprivatekey-sample"></a>Esempio FindPrivateKey

Può essere difficile individuare il percorso e il nome del file di chiave privata associati a un certificato X.509 specifico nell'archivio certificati. Lo strumento FindPrivateKey.exe facilita questo processo.

> [!IMPORTANT]
> FindPrivateKey è un esempio che deve essere compilato prima dell'utilizzo. Per istruzioni su come compilare lo strumento FindPrivateKey, vedere la sezione [per compilare il progetto FindPrivateKey](#to-build-the-findprivatekey-project) .

I certificati X.509 vengono installati da un amministratore o da qualsiasi utente nel computer. Tuttavia, il certificato può essere accessibile da un servizio in esecuzione con un account diverso. Ad esempio, l'account servizio di rete.

Questo account può non avere accesso al file di chiave privata se il certificato non è stato originariamente installato. Lo strumento FindPrivateKey fornisce il percorso del file di chiave privata di un determinato certificato X.509. È possibile aggiungere o rimuovere autorizzazioni quando si conosce il percorso del file di chiave privata degli specifici certificati X.509.

Gli esempi che utilizzano certificati per la sicurezza utilizzano lo strumento FindPrivateKey nel file *Setup. bat* . Una volta trovato il file di chiave privata, è possibile utilizzare altri strumenti, ad esempio *cacls. exe* , per impostare i diritti di accesso appropriati sul file.

Quando si esegue un servizio Windows Communication Foundation (WCF) con un account utente, ad esempio un file eseguibile indipendente, assicurarsi che l'account utente disponga dell'accesso in sola lettura al file. Quando si esegue un servizio WCF in Internet Information Services (IIS) gli account predefiniti in cui viene eseguito il servizio sono il servizio di rete in IIS 7 e le versioni precedenti oppure l'identità del pool di applicazioni in IIS 7,5 e versioni successive. Per altre informazioni, vedere [identità del pool di applicazioni](/iis/manage/configuring-security/application-pool-identities).

## <a name="examples"></a>Esempi

Quando si accede a un certificato per il quale il processo non dispone dei privilegi di lettura, viene visualizzato un messaggio di eccezione simile all'esempio seguente:

```output
System.ArgumentException was unhandled
Message="The certificate 'CN=localhost' must have a private key that is capable of key exchange.  The process must have access rights for the private key."
Source="System.ServiceModel"
```

Quando si verifica questo problema, utilizzare lo strumento FindPrivateKey per trovare il file di chiave privata, quindi impostare il diritto di accesso per il processo in cui viene eseguito il servizio. Ad esempio, questa operazione può essere eseguita con lo strumento Cacls. exe, come illustrato nell'esempio seguente:

```console
cacls.exe "C:\Documents and Settings\All Users\Application Data\Microsoft\Crypto\RSA\MachineKeys\8aeda5eb81555f14f8f9960745b5a40d_38f7de48-5ee9-452d-8a5a-92789d7110b1" /E /G "NETWORK SERVICE":R
```

#### <a name="to-build-the-findprivatekey-project"></a>Per compilare il progetto FindPrivateKey

Per scaricare il progetto, visitare gli [esempi Windows Communication Foundation (WCF) e Windows Workflow Foundation (WF) per .NET Framework 4](https://www.microsoft.com/download/details.aspx?id=21459).

1. Aprire Esplora file e passare alla cartella *WF_WCF_Samples \wcf\setup\findprivatekey\cs* nel percorso della directory in cui è stato installato l'esempio.

2. Fare doppio clic sull'icona del file con estensione sln per aprirlo in Visual Studio.

3. Scegliere **Ricompila soluzione**dal menu **Compila** .

4. La compilazione della soluzione genera il file FindPrivateKey.exe.

## <a name="conventionscommand-line-entries"></a>Convenzioni-voci della riga di comando

 "[*opzione*]" rappresenta un set facoltativo di parametri.

 "{*Option*}" rappresenta un set obbligatorio di parametri.

 "*opzione1* &#124; *opzione2*" rappresenta una scelta tra set di opzioni.

 "\<*valore*>" rappresenta un valore di parametro da immettere.

## <a name="usage"></a>Usage

```console
FindPrivateKey <storeName> <storeLocation> [{ {-n <subjectName>} | {-t <thumbprint>} } [-f | -d | -a]]
```

Dove:

| Parametro         | Descrizione                                                                       |
|-----------------|-----------------------------------------------------------------------------------|
| `<subjectName>` | Nome del soggetto del certificato                                               |
| `<thumbprint>`  | Identificazione personale del certificato. è possibile utilizzare lo strumento Certmgr. exe per trovarlo. |
| `-f`            | solo nome file di output                                                             |
| `-d`            | solo directory di output                                                             |
| `-a`            | nome file assoluto di output                                                         |

Se al prompt dei comandi non viene specificato alcun parametro, viene visualizzato il testo della guida con queste informazioni.

## <a name="examples"></a>Esempi

Questo esempio trova il nome del file del certificato con un nome soggetto "CN = localhost", nell'archivio personale dell'utente corrente.

```console
FindPrivateKey My CurrentUser -n "CN=localhost"
```

In questo esempio viene trovato il nome del file del certificato con un nome soggetto "CN = localhost" nell'archivio personale dell'utente corrente e viene restituito il percorso completo della directory.

```console
FindPrivateKey My CurrentUser -n "CN=localhost" -a
```

In questo esempio viene ricercato il nome del file del certificato con un'identificazione digitale di "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52", nell'archivio Personale del computer locale.

```console
FindPrivateKey My LocalMachine -t "03 33 98 63 d0 47 e7 48 71 33 62 64 76 5c 4c 9d 42 1d 6b 52"
```
