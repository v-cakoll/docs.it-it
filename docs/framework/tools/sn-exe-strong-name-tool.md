---
title: Sn.exe (strumento Nome sicuro)
ms.date: 03/30/2017
helpviewer_keywords:
- public keys, signing files
- Strong Name tool
- Sn.exe
- assemblies [.NET Framework], signing
- signing files
- strong-named assemblies, signing files
- key pairs for signing files
ms.assetid: c1d2b532-1b8e-4c7a-8ac5-53b801135ec6
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 02568de0a1cc5cec6b92e646e000e69ae79b1646
ms.sourcegitcommit: d9a0071d0fd490ae006c816f78a563b9946e269a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/25/2019
ms.locfileid: "55066389"
---
# <a name="snexe-strong-name-tool"></a>Sn.exe (strumento Nome sicuro)
Lo strumento Nome sicuro (Sn.exe) consente di firmare assembly con [nomi sicuri](../../../docs/framework/app-domains/strong-named-assemblies.md). Lo strumento offre diverse opzioni per la gestione delle chiavi e la generazione e la verifica delle firme.  
  
> [!WARNING]
> Non usare i nomi sicuri per la sicurezza, poiché forniscono solo un'identità univoca.

 Per altre informazioni sui nomi sicuri e sugli assembly con nomi sicuri, vedere [Assembly con nomi sicuri](../../../docs/framework/app-domains/strong-named-assemblies.md) e [Procedura: Firmare un assembly con un nome sicuro](../../../docs/framework/app-domains/how-to-sign-an-assembly-with-a-strong-name.md).  
  
 Lo strumento Nome Sicuro viene installato automaticamente con Visual Studio. Per avviare lo strumento, usare il prompt dei comandi per lo sviluppatore (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  

> [!NOTE]
>  Nei computer a 64 bit eseguire la versione a 32 bit di Sn.exe tramite il Prompt dei comandi per gli sviluppatori per Visual Studio e la versione a 64 bit tramite il prompt dei comandi di Visual Studio x64 Win64. 
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
sn [-quiet][option [parameter(s)]]  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Opzione|Description|  
|------------|-----------------|  
|**-a** *fileCoppiaChiaviIdentità* *fileChiavePubblicaFirma*|Genera dati <xref:System.Reflection.AssemblySignatureKeyAttribute> per eseguire la migrazione della chiave di identità alla chiave di firma da un file.|  
|**-ac** *fileChiavePubblicaIdentità* *contenitoreCoppiaChiaviIdentità* *fileChiavePubblicaIdentità*|Genera dati <xref:System.Reflection.AssemblySignatureKeyAttribute> per eseguire la migrazione della chiave di identità alla chiave di firma da un contenitore di chiavi.|  
|**-c** [*csp*]|Imposta il provider del servizio di crittografia (CSP) predefinito da usare per la firma con nome sicuro. Questa impostazione ha effetto sull'intero computer. Se non si specifica alcun nome CSP, l'impostazione corrente viene cancellata.|  
|**-d** *contenitore*|Elimina dal CSP del nome sicuro il contenitore delle chiavi specificato.|  
|**-D**  *assembly1 assembly2*|Verifica che due assembly differiscano solo nella firma. Questa opzione è spesso usata come controllo dopo che un assembly è stato nuovamente firmato con una coppia di chiavi differente.|  
|**-e**  *assembly FileOut*|Estrae la chiave pubblica da *assembly* e la archivia in *FileOut*.|  
|**-h**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**-i** *FileIn contenitore*|Installa la coppia di chiavi da *FileIn* nel contenitore di chiavi specificato. Il contenitore delle chiavi si trova nel CSP del nome sicuro.|  
|**-k** [*dimensionechiave*] *FileOut*|Genera una nuova chiave <xref:System.Security.Cryptography.RSACryptoServiceProvider> con la dimensione indicata e la scrive nel file specificato.  Nel file vengono scritte sia la chiave pubblica sia la chiave privata.<br /><br /> Se non si specifica una dimensione per la chiave, verrà generata una chiave a 1024 bit se è installato Microsoft Enhanced Cryptographic Provider; in caso contrario, verrà generata una chiave a 512 bit.<br /><br /> Il parametro *dimensionechiave* supporta lunghezze di chiavi da 384 bit a 16384 bit ad incrementi di 8 bit, se è installato Microsoft Enhanced Cryptographic Provider.  Se è stato installato Microsoft Base Cryptographic Provider, supporta lunghezze di chiave da 384 a 512 bit per incrementi di 8 bit.|  
|**-m** [**y** *&#124;* **n**]|Indica se i contenitori delle chiavi sono specifici del computer o dell'utente. Se si specifica *y*, i contenitori delle chiavi sono specifici del computer. Se si specifica *n*, i contenitori delle chiavi sono specifici dell'utente.<br /><br /> Se non si specifica né y né n, questa opzione visualizzerà l'impostazione corrente.|  
|**-o**  *FileIn* [*FileOut*]|Estrae la chiave pubblica da *FileIn* e la archivia in un file CSV. I byte della chiave pubblica sono separati da virgole. Questo formato è utile per gestire i riferimenti hardcoded alle chiavi sotto forma di matrici inizializzate nel codice sorgente. Se non si specifica un *FileOut*, questa opzione inserirà l'output negli Appunti. **Nota:**  Questa opzione non verifica che l'input sia solo una chiave pubblica. Se in `infile` è contenuta una coppia di chiavi con una chiave privata, verrà estratta anche la chiave privata.|  
|**-p** *FileIn FileOut* [*algoritmohash*]|Estrae la chiave pubblica dalla coppia di chiavi in *FileIn* e la archivia in *FileOut*, eventualmente usando l'algoritmo RSA specificato da *algoritmohash*. È possibile usare questa chiave pubblica per ritardare la firma di un assembly tramite le opzioni **/delaysign+** e **/keyfile** di [Assembly Linker (Al.exe)](../../../docs/framework/tools/al-exe-assembly-linker.md). Quando per un assembly è impostata la firma ritardata, in fase di compilazione viene impostata solo la chiave pubblica e nel file viene riservato spazio per la firma che verrà aggiunta in un secondo momento, quando sarà nota la chiave privata.|  
|**-pc**  *contenitore* *FileOut* [*algoritmohash*]|Estrae la chiave pubblica dalla coppia di chiavi in *contenitore* e la archivia in *FileOut*. Se si usa l'opzione *algoritmohash*, viene usato l'algoritmo RSA per estrarre la chiave pubblica.|  
|**-Pb** [**y** *&#124;* **n**]|Specifica se sono applicati i criteri per ignorare i nomi sicuri. Se si specifica *y*, i nomi sicuri per gli assembly con attendibilità totale non vengono convalidati se caricati in <xref:System.AppDomain> con attendibilità totale. Se si specifica *n*, i nomi sicuri vengono convalidati per verificare se sono corretti, ma non per individuare un nome sicuro specifico. <xref:System.Security.Permissions.StrongNameIdentityPermission> non ha effetto sugli assembly con attendibilità totale. È necessario eseguire un controllo manuale per rilevare una corrispondenza di nomi sicuri.<br /><br /> Se non si specifica né `y` né `n`, questa opzione visualizzerà l'impostazione corrente. Il valore predefinito è `y`. **Nota:**  Nei computer a 64 bit è necessario impostare questo parametro sia nell'istanza di Sn.exe a 32 bit che in quella a 64 bit.|  
|**-q**[**uiet**]|Specifica la modalità non interattiva. Evita la visualizzazione dei messaggi di esito positivo.|  
|**-R**[**a**] *assembly* *FileIn*|Firma nuovamente un assembly firmato in precedenza o con firma ritardata con la coppia di chiavi presente in *FileIn*.<br /><br /> Se si usa **-Ra**, vengono ricalcolati gli hash per tutti i file nell'assembly.|  
|**-Rc**[**a**] *assembly contenitore*|Firma nuovamente un assembly firmato in precedenza o con firma ritardata con la coppia di chiavi presente in *contenitore*.<br /><br /> Se si usa **-Rca**, vengono ricalcolati gli hash per tutti i file nell'assembly.|  
|**-Rh** *assembly*|Ricalcola gli hash per tutti i file dell'assembly.|  
|**-t**[**p**] *FileIn*|Visualizza il token per la chiave pubblica archiviata in *FileIn*. Il contenuto di *FileIn* deve includere una chiave pubblica generata in precedenza da un file di coppia di chiavi tramite **-p**.  Non usare l'opzione **-t[p]** per estrarre il token direttamente dal file di coppia di chiavi.<br /><br /> Sn.exe calcola il token usando una funzione hash tratta dalla chiave pubblica. Per risparmiare spazio, Common Language Runtime archivia i token di chiave pubblica nel manifesto come parte di un riferimento a un altro assembly quando registra una dipendenza in un assembly con nome sicuro. Oltre al token, l'opzione **-tp** visualizza anche la chiave pubblica. Se all'assembly è stato applicato l'attributo <xref:System.Reflection.AssemblySignatureKeyAttribute>, il token è per la chiave di identità e viene visualizzato il nome dell'algoritmo hash e della chiave di identità.<br /><br /> Questa opzione non verifica la firma dell'assembly e non deve essere usata per prendere decisioni sull'attendibilità.  Serve solo a visualizzare i dati non elaborati del token della chiave pubblica.|  
|**-T**[**p**] *assembly*|Visualizza il token della chiave pubblica per *assembly*. *assembly* deve corrispondere al nome di un file che contiene un manifesto dell'assembly.<br /><br /> Sn.exe calcola il token usando una funzione hash tratta dalla chiave pubblica. Per risparmiare spazio, il runtime archivia i token di chiave pubblica nel manifesto come parte di un riferimento a un altro assembly quando registra una dipendenza in un assembly con nome sicuro. Oltre al token, l'opzione **-Tp** visualizza anche la chiave pubblica. Se all'assembly è stato applicato l'attributo <xref:System.Reflection.AssemblySignatureKeyAttribute>, il token è per la chiave di identità e viene visualizzato il nome dell'algoritmo hash e della chiave di identità.<br /><br /> Questa opzione non verifica la firma dell'assembly e non deve essere usata per prendere decisioni sull'attendibilità.  Serve solo a visualizzare i dati non elaborati del token della chiave pubblica.|  
|`-TS` `assembly` `infile`|Applica la firma di test all'`assembly` firmato o parzialmente firmato con la coppia di chiavi presente in `infile`.|  
|-`TSc` `assembly` `container`|Applica la firma di test all'`assembly` firmato o parzialmente firmato con la coppia di chiavi presente nel contenitore di chiavi `container`.|  
|**-v** *assembly*|Verifica il nome sicuro in *assembly*, dove *assembly* è il nome di un file che contiene un manifesto dell'assembly.|  
|**-vf**  *assembly*|Verifica il nome sicuro in *assembly*. A differenza dall'opzione **-v**, **-vf** forza la verifica, anche se questa è stata disabilitata tramite l'opzione **-Vr**.|  
|**-Vk**  *regfile.reg* *assembly* [*elencoutenti*] [*FileIn*]|Crea un file con voci di registrazione (.reg) che è possibile usare per registrare l'assembly specificato e poter saltare la verifica. Le regole di denominazione dell'assembly che si applicano all'opzione **-Vr** si applicano anche a **–Vk**. Per informazioni sulle opzioni *elencoutenti* e *FileIn*, vedere l'opzione **–Vr**.|  
|**-Vl**|Elenca le impostazioni correnti per la verifica del nome sicuro nel computer.|  
|**-Vr**  *assembly* [*elencoutenti*] [*FileIn*]|Registra *assembly* per evitare la verifica. Facoltativamente, è possibile specificare un elenco delimitato da virgole di nomi utente a cui applicare il salto della verifica. Se si specifica *FileIn*, la verifica resta abilitata, ma nelle operazioni di verifica verrà usata la chiave pubblica contenuta in *FileIn*. È possibile specificare *assembly* nel formato *\*, nomesicuro* per registrare tutti gli assembly con il nome sicuro specificato. Per *nomesicuro*, specificare la stringa di cifre esadecimali che rappresenta la chiave pubblica in formato token. Vedere le opzioni **-t** e **-T** per visualizzare il token della chiave pubblica. **Attenzione:**  Usare questa opzione solo durante lo sviluppo. L'aggiunta di un assembly all'elenco di omissione della verifica rende vulnerabile il sistema di sicurezza. Un assembly dannoso potrebbe usare il nome completamente specificato (nome assembly, versione, impostazioni cultura e token della chiave pubblica) dell'assembly aggiunto all'elenco di omissione della verifica per camuffare la propria identità. La verifica verrebbe omessa quindi anche per l'assembly dannoso.|  
|||  
|**-Vu**  *assembly*|Annulla la registrazione di *assembly* per evitare la verifica. Le regole per la denominazione delle assembly applicate a **-Vr** vengono anche applicate a **-Vu**.|  
|**-Vx**|Rimuove tutte le voci di salto della verifica.|  
|**-?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
> [!NOTE]
>  Per essere valide, le opzioni di Sn.exe devono essere digitate esattamente come indicato, rispettando con precisione la combinazione di maiuscole e minuscole.  
  
## <a name="remarks"></a>Note  
 Le opzioni **-R** e **–Rc** sono utili con gli assembly per cui è stata impostata la firma ritardata. In questo scenario solo la chiave pubblica viene impostata in fase di compilazione e la firma viene apposta in un secondo tempo, quando sarà nota la chiave privata.  
  
> [!NOTE]
>  Per i parametri come –**Vr** che scrivono in risorse protette, ad esempio il Registro di sistema, eseguire SN.exe come amministratore.  
  
Lo strumento Nome sicuro presuppone che vengano generate coppie di chiavi pubblica/privata con l'identificatore dell'algoritmo `AT_SIGNATURE`. Le coppie di chiavi pubblica/privata generate con l'algoritmo `AT_KEYEXCHANGE` restituiscono un errore. 

## <a name="examples"></a>Esempi  
 Il comando che segue crea una nuova coppia casuale di chiavi e la archivia in `keyPair.snk`.  
  
```  
sn -k keyPair.snk  
```  
  
 Il comando che segue archivia la chiave presente in `keyPair.snk` all'interno del contenitore `MyContainer` nel CSP del nome sicuro.  
  
```  
sn -i keyPair.snk MyContainer  
```  
  
 Il comando che segue estrae la chiave pubblica da `keyPair.snk` e la archivia in `publicKey.snk`.  
  
```  
sn -p keyPair.snk publicKey.snk  
```  
  
 Il comando che segue visualizza la chiave pubblica e il token per la chiave pubblica contenuti in `publicKey.snk`.  
  
```  
sn -tp publicKey.snk  
```  
  
 Il comando che segue verifica l'assembly `MyAsm.dll`.  
  
```  
sn -v MyAsm.dll  
```  
  
 Il comando che segue elimina `MyContainer` dal CSP predefinito.  
  
```  
sn -d MyContainer  
```  
  
## <a name="see-also"></a>Vedere anche
- [Strumenti](../../../docs/framework/tools/index.md)
- [Al.exe (Assembly Linker)](../../../docs/framework/tools/al-exe-assembly-linker.md)
- [Assembly con nomi sicuri](../../../docs/framework/app-domains/strong-named-assemblies.md)
- [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md)
