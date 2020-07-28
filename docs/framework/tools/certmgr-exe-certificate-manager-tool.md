---
title: Certmgr.exe (strumento di gestione certificati)
description: Esplorare Certmgr.exe, lo strumento Gestione certificati. Questo strumento gestisce i certificati, gli elenchi di certificati attendibili (scopi consentiti) e gli elenchi di revoche di certificati (CRL).
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- certificates, managing
- CRLs
- certificate trust lists
- Certmgr.exe
- Certificate Manager tool
- CTLs
- certificate revocation lists
ms.assetid: 7e953b43-1374-4bbc-814f-53ca1b6b52bb
ms.openlocfilehash: 43ab281e6ec28ff23ea584b03fd4278c6682e33e
ms.sourcegitcommit: 87cfeb69226fef01acb17c56c86f978f4f4a13db
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/24/2020
ms.locfileid: "87167260"
---
# <a name="certmgrexe-certificate-manager-tool"></a>Certmgr.exe (strumento di gestione certificati)
Lo strumento di gestione certificati (Certmgr.exe) gestisce certificati, elenchi di scopi consentiti ai certificati ed elenchi di revoche di certificati (CRL, Certificate Revocation List).  
  
 Lo strumento viene installato automaticamente insieme a Visual Studio. Per avviare lo strumento, utilizzare il [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
> [!NOTE]
> Lo strumento di gestione dei certificati (Certmgr.exe) è un'utilità da riga di comando, da non confondere con lo snap-in certificati (Certmgr.msc) di Microsoft Management Console (MMC). Poiché Certmgr.msc in genere si trova nella directory di sistema di Windows, l'immissione di `certmgr` nella riga di comando potrebbe caricare lo snap-in di MMC Certificati anche se è stato aperto il Prompt dei comandi per gli sviluppatori per Visual Studio. Questo accade perché il percorso dello snap-in precede il percorso dello strumento di gestione dei certificati nella variabile di ambiente PATH. Se si verifica questo problema, è possibile eseguire i comandi Certmgr.exe specificando il percorso dell'eseguibile.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Per una panoramica dei certificati X.509, vedere [Utilizzo dei certificati](../wcf/feature-details/working-with-certificates.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
      certmgr [/add | /del | /put] [options]  
[/s[/r registryLocation]] [sourceStorename]  
[/s[/r registryLocation]] [destinationStorename]  
```  
  
## <a name="parameters"></a>Parametri  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|*sourceStorename*|Archivio certificati contenente certificati, elenchi di scopi consentiti ai certificati o CRL da aggiungere, eliminare, salvare o visualizzare. Può trattarsi di un file di archivio o di un archivio di sistema.|  
|*destinationStorename*|File o archivio certificati di output.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/Add**|Aggiunge certificati, elenchi di scopi consentiti ai certificati e CRL a un archivio certificati.|  
|**/All**|Aggiunge tutte le voci se usata con **/add**, Elimina tutte le voci se utilizzate con **/del**. Visualizza tutte le voci se usate senza le opzioni **/Add** o **/del** . Non è possibile usare l'opzione **/all** con **/put**.|  
|**/c**|Aggiunge i certificati se usata con **/add**, Elimina i certificati se utilizzati con **/del**. Salva i certificati se usati con **/put**. Visualizza certificati quando usata senza le opzioni **/add**, **/del** o **/put**.|  
|**/CRL**|Aggiunge i CRL se usata con **/add**, Elimina i CRL se utilizzati con **/del**. Salva i CRL se utilizzati con **/put**. Visualizza CRL quando usata senza le opzioni **/add**, **/del** o **/put**.|  
|**/CTL**|Aggiunge gli elenchi di scopi consentiti se usata con **/add**, Elimina scopi consentiti se usato con **/del**. Salva scopi consentiti se usato con **/put**. Visualizza gli elenchi di scopi consentiti quando usata senza le opzioni **/add**, **/del** o **/put**.|  
|**/del**|Elimina certificati, elenchi di scopi consentiti e CRL da un archivio certificati.|  
|**/e** *encodingType*|Specifica il tipo di codifica dei certificati. Il valore predefinito è `X509_ASN_ENCODING`.|  
|**/f** *dwFlags*|Specifica il flag di archivio aperto. Si tratta del parametro *dwFlags* passato a **CertOpenStore**. Il valore predefinito è CERT_SYSTEM_STORE_CURRENT_USER. Questa opzione viene considerata solo se viene usata l'opzione **/y**.|  
|**/h**[**ELP**]|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/n** *nam*|Specifica il nome comune del certificato da aggiungere, eliminare o salvare. È possibile usare questa opzione solo con certificati, non con elenchi di scopi consentiti o CRL.|  
|**/Put**|Salva su file un certificato X.509, un elenco di scopi consentiti o un CRL da un archivio certificati. Il file viene salvato nel formato X.509. È possibile usare l'opzione **/7** con l'opzione **/put** per salvare il file nel formato PKCS #7. L'opzione **/put** deve essere seguita da **/c**, **/CTL** o **/CRL**. Non è possibile usare l'opzione **/all** con **/put**.|  
|**/r** *location*|Identifica la posizione dell'archivio di sistema all'interno del Registro di sistema. Questa opzione viene considerata solo se viene specificata l'opzione **/s**. *location* deve essere uno degli elementi seguenti:<br /><br /> -   `currentUser` indica che l'archivio certificati si trova sotto la chiave HKEY_CURRENT_USER. Questa è la modalità predefinita.<br />-   `localMachine` indica che l'archivio certificati si trova sotto la chiave HKEY_LOCAL_MACHINE.|  
|**/s**|Indica che l'archivio certificati è un archivio di sistema. Se non si specifica questa opzione, l'archivio viene considerato come **StoreFile**.|  
|**/sha1** *sha1Hash*|Specifica l'hash SHA1 del certificato, dell'elenco di scopi consentiti o del CRL da aggiungere, eliminare o salvare.|  
|**/v**|Specifica la modalità dettagliata. Visualizza informazioni dettagliate su certificati, elenchi di scopi consentiti e CRL. Non è possibile usare questa opzione con le opzioni **/add**, **/del** o **/put**.|  
|**/y** *provider*|Specifica il nome del provider dell'archivio.|  
|**/7**|Salva l'archivio di destinazione come oggetto PKCS #7.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
## <a name="remarks"></a>Osservazioni  
 Certmgr.exe svolge le seguenti funzioni di base:  
  
- Visualizza certificati, elenchi di scopi consentiti e CRL sulla console.  
  
- Aggiunge certificati, elenchi di scopi consentiti ai certificati e CRL a un archivio certificati.  
  
- Elimina certificati, elenchi di scopi consentiti e CRL da un archivio certificati.  
  
- Salva su file un certificato X.509, un elenco di scopi consentiti o un CRL da un archivio certificati.  
  
 Certmgr.exe funziona con due tipi di archivi certificati: **StoreFile** e archivi di sistema. Non è necessario specificare il tipo di archivio certificati: Certmgr.exe è infatti in grado di identificare il tipo di archivio e di eseguire le operazioni appropriate.  
  
 Se Certmgr.exe viene eseguito senza specificare alcuna opzione, verrà avviato lo snap-in certmgr.msc, che comprende una GUI che assisterà l'utente nell'esecuzione delle attività di gestione dei certificati disponibili anche dalla riga di comando. La GUI fornisce una procedura guidata di importazione che consente di copiare certificati, elenchi di scopi consentiti e CRL dal disco a un archivio certificati.  
  
 È possibile trovare i nomi degli archivi X509Certificate per i parametri `sourceStorename` e `destinationStorename` compilando ed eseguendo il codice seguente.  
  
 [!code-csharp[Tools.CertMgr#1](../../../samples/snippets/csharp/VS_Snippets_CLR/tools.certmgr/cs/storenames1.cs#1)]
 [!code-vb[Tools.CertMgr#1](../../../samples/snippets/visualbasic/VS_Snippets_CLR/tools.certmgr/vb/storenames1.vb#1)]  
  
 Per altre informazioni sui certificati, vedere [Utilizzo dei certificati](../wcf/feature-details/working-with-certificates.md).  
  
## <a name="examples"></a>Esempi  
 Il comando che segue visualizza un archivio di sistema predefinito denominato `my` con output dettagliato.  
  
```console  
certmgr /v /s my  
```  
  
 Il comando che segue aggiunge tutti i certificati contenuti in un file denominato `myFile.ext` in un nuovo file denominato `newFile.ext`.  
  
```console  
certmgr /add /all /c myFile.ext newFile.ext  
```  
  
 Il comando che segue aggiunge il certificato contenuto in un file denominato `testcert.cer` all'archivio di sistema `my`.  
  
```console  
certmgr /add /c testcert.cer /s my  
```  
  
 Il comando che segue aggiunge il certificato contenuto in un file denominato `TrustedCert.cer` all'archivio certificati radice.  
  
```console  
certmgr /c /add TrustedCert.cer /s root  
```  
  
 Il comando che segue salva un certificato con il nome comune `myCert` contenuto nell'archivio di sistema `my` in un file denominato `newCert.cer`.  
  
```console  
certmgr /add /c /n myCert /s my newCert.cer  
```  
  
 Il comando che segue elimina tutti gli elenchi di scopi consentiti contenuti nell'archivio di sistema `my` e salva l'archivio ottenuto in un file denominato `newStore.str`.  
  
```console  
certmgr /del /all /ctl /s my newStore.str  
```  
  
 Il comando che segue salva nel file `my` un certificato contenuto nell'archivio di sistema `newFile`. Verrà chiesto di inserire il numero del certificato presente in `my` per inserirlo in `newFile`.  
  
```console  
certmgr /put /c /s my newFile  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Makecert.exe (Certificate Creation Tool)](/windows/desktop/SecCrypto/makecert) (Makecert.exe, strumento di creazione certificati)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
