---
title: Tlbimp.exe (utilità di importazione della libreria dei tipi)
ms.date: 03/30/2017
helpviewer_keywords:
- type libraries [.NET Framework], importing
- importing type library
- Tlbimp.exe
- type definition conversion
- Type Library Importer
- type libraries
- converting type definitions
ms.assetid: ec0a8d63-11b3-4acd-b398-da1e37e97382
ms.openlocfilehash: d942378888b06049022188c75456f438d4b187e3
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180238"
---
# <a name="tlbimpexe-type-library-importer"></a>Tlbimp.exe (utilità di importazione della libreria dei tipi)
L'utilità di importazione della libreria dei tipi consente di convertire le definizioni dei tipi presenti in una libreria dei tipi COM nelle definizioni equivalenti in un assembly di Common Language Runtime. L'output di Tlbimp.exe è un file binario (assembly) che contiene i metadati di runtime per i tipi definiti all'interno della libreria dei tipi originale. È possibile esaminare questo file con strumenti quali [Ildasm.exe](ildasm-exe-il-disassembler.md).  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
tlbimp tlbFile [options]  
```  
  
## <a name="parameters"></a>Parametri  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|*tlbFile*|Nome di un file che contiene una libreria dei tipi COM.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/asmversion:** *versionnumber*|Specifica il numero di versione dell'assembly da produrre. Specificare* versionnumber* nel *formato major.minor.build.revision*.|  
|**/azienda:**`companyinformation`|Aggiunge le informazioni sulla società all'assembly di output.|  
|**/copyright:**`copyrightinformation`|Aggiunge le informazioni sul copyright all'assembly di output. Queste informazioni possono essere visualizzate nella finestra di dialogo **Proprietà file** dell'assembly.|  
|**/delaysign (firma)**|Indica a Tlbimp.exe di firmare l'assembly risultante con un nome sicuro utilizzando la firma ritardata. È necessario specificare questa opzione con **/keycontainer:**, **/keyfile:** o **/publickey:**. Per altre informazioni sulla firma ritardata, vedere [Ritardo della firma di un assembly](../../standard/assembly/delay-sign.md).|  
|**/help**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/keycontainer:** *containername*|Firma l'assembly risultante con un nome sicuro usando la coppia di chiavi pubblica/privata presente nel contenitore di chiavi specificato da *containername*.|  
|**/keyfile:** *filename*|Firma l'assembly risultante con un nome sicuro usando la coppia di chiavi pubblica/privata ufficiale dell'editore trovata in *filename*.|  
|**/machine:**`machinetype`|Crea un assembly destinato al tipo di computer specificato (microprocessore). Tipi di computer supportati: x86, x64, Itanium e Agnostic.|  
|**/namespace:** *namespace*|Specifica lo spazio dei nomi in cui si desidera produrre l'assembly.|  
|**/noclassmembers**|Impedisce a Tlbimp.exe di aggiungere membri alle classi. In questo modo è possibile evitare un potenziale oggetto <xref:System.TypeLoadException>.|  
|**/nologo**|Evita la visualizzazione del messaggio di avvio Microsoft.|  
|**/out:** *nome file*|Specifica il nome del file di output, l'assembly e lo spazio dei nomi in cui scrivere le definizioni dei metadati. L'opzione **/out** non influisce sullo spazio dei nomi dell'assembly se la libreria dei tipi specifica l'attributo personalizzato del linguaggio di definizione dell'interfaccia (IDL, Interface Definition Language) che controlla in modo esplicito lo spazio dei nomi dell'assembly. Se non si specifica questa opzione, i metadati vengono scritti in un file avente lo stesso nome della libreria dei tipi definita all'interno del file di input e l'estensione .dll. Se il file di output ha lo stesso nome del file di input, lo strumento genera un errore al fine di non sovrascrivere la libreria dei tipi.|  
|**/primary**|Produce un assembly di interoperabilità primario per la libreria dei tipi specificata. All'assembly vengono aggiunte informazioni che indicano che l'assembly è prodotto dall'editore della libreria dei tipi. Specificando un assembly di interoperabilità primario, si rende differente l'assembly di un editore da qualsiasi altro assembly creato dalla libreria dei tipi utilizzando Tlbimp.exe. È opportuno che l'opzione **/primary** venga usata solo dall'editore della libreria dei tipi in corso di importazione con Tlbimp.exe. Si noti che è necessario firmare un assembly di interoperabilità primario con un [nome sicuro](../../standard/assembly/strong-named.md). Per altre informazioni, vedere [Assembly di interoperabilità primari](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/aax7sdch(v=vs.100)).|  
|**/prodotto:**`productinformation`|Aggiunge le informazioni sul prodotto all'assembly di output. Queste informazioni possono essere visualizzate nella finestra di dialogo **Proprietà file** dell'assembly.|  
|**/productversion:**`productversioninformation`|Aggiunge le informazioni sulla versione del prodotto all'assembly di output. Non esistono restrizioni di formato. Queste informazioni possono essere visualizzate nella finestra di dialogo **Proprietà file** dell'assembly.|  
|**/publickey:** *filename*|Specifica il file che contiene la chiave pubblica da utilizzare per firmare l'assembly risultante. Se si specifica l'opzione **/keyfile:** o **/keycontainer:** anziché **/publickey:**, la chiave pubblica viene generata dalla coppia di chiavi pubblica/privata fornita con **/keyfile:** o **/keycontainer:**. L'opzione **/publickey:** supporta scenari di firma ritardata e chiavi di test. Il file è nel formato generato da Sn.exe. Per altre informazioni, vedere l'opzione **-p** di Sn.exe in [Sn.exe (strumento Nome sicuro)](sn-exe-strong-name-tool.md).|  
|**/reference:** *filename*|Specifica il file di assembly da utilizzare per risolvere i riferimenti a tipi definiti all'esterno della libreria dei tipi corrente. Se non si specifica l'opzione **/reference**, viene importata automaticamente in modo ricorsivo qualsiasi libreria dei tipi esterna a cui faccia riferimento la libreria dei tipi che viene importata. Se si specifica l'opzione **/reference**, lo strumento tenta di risolvere i tipi esterni negli assembly a cui si fa riferimento prima di importare altre librerie dei tipi.|  
|**/silence:** `warningnumber`|Non visualizza l'avviso specificato. Questa opzione non può essere usata con **/silent**.|  
|**/silent**|Evita la visualizzazione dei messaggi di operazione riuscita. Questa opzione non può essere usata con **/silence**.|  
|**/strictref**|Non esegue l'importazione della libreria dei tipi se non è possibile risolvere tutti i riferimenti all'interno dell'assembly corrente, degli assembly specificati con l'opzione **/reference** o degli assembly di interoperabilità primari registrati.|  
|**/strictref:nopia**|Opzione analoga a **/strictref**, ma ignora gli assembly di interoperabilità primari.|  
|**/sysarray**|Indica allo strumento di importare un SafeArray in stile COM come tipo di <xref:System.Array> gestito.|  
|**/tlbreference:** *filename*|Specificare il file della libreria dei tipi da utilizzare per risolvere i riferimenti alla libreria dei tipi senza consultare il Registro di sistema.<br /><br /> Se si utilizza questa opzione non verranno caricati alcuni formati precedenti di librerie dei tipi.  È comunque possibile caricare i formati precedenti di librerie dei tipi in modo implicito mediante il Registro di sistema o la directory corrente.|  
|**/marchio:**`trademarkinformation`|Aggiunge le informazioni sul marchio all'assembly di output. Queste informazioni possono essere visualizzate nella finestra di dialogo **Proprietà file** dell'assembly.|  
|**/transform:** *transformname*|Trasforma i metadati come specificato dal parametro *transformname*.<br /><br /> Specificare **dispret** per il parametro *transformname* per trasformare i parametri [out, retval] dei metodi su interfacce solo dispatch (dispinterfaces) in valori restituiti.<br /><br /> Per ulteriori informazioni su questa opzione, vedere gli esempi più avanti in questo argomento.|  
|**/non sicuro**|Produce interfacce senza controlli di sicurezza di .NET Framework. Chiamare un metodo esposto in questo modo può comportare rischi di sicurezza. Non utilizzare questa opzione a meno che non si conoscano i rischi derivanti dall'esposizione di codice di questo tipo.|  
|**/verbose (in inglese)**|Specifica la modalità dettagliata e visualizza informazioni aggiuntive sulla libreria dei tipi importata.|  
|**/VariantBoolFieldToBool**|Converte i campi `VARIANT_BOOL` nelle strutture in <xref:System.Boolean>.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
> [!NOTE]
> Le opzioni della riga di comando di Tlbimp.exe non sono soggette alla distinzione tra maiuscole e minuscole e per specificarle non è necessario seguire un ordine particolare. Per identificarle in modo univoco, è sufficiente digitare solo una parte dell'opzione. Pertanto, **/n** equivale a **/nologo** e **/ou:** *outfile.dll* equivale a **/out:** *outfile.dll*.  
  
## <a name="remarks"></a>Osservazioni  
 Tlbimp.exe converte un'intera libreria dei tipi in blocco. Non è possibile utilizzare lo strumento per generare informazioni sui tipi per un subset dei tipi definiti in una singola libreria dei tipi.  
  
 Spesso risulta utile o necessario poter assegnare agli assembly [nomi sicuri](../../standard/assembly/strong-named.md). Pertanto, Tlbimp.exe include opzioni che permettono di fornire le informazioni necessarie alla generazione di assembly con nomi sicuri. Entrambe le opzioni **/keyfile:** e **/keycontainer:** consentono di firmare gli assembly con nomi sicuri. Pertanto, è sufficiente specificare solo una di queste opzioni alla volta.  
  
 È possibile specificare più assembly di riferimento usando l'opzione **/reference** più volte.

 A causa del modo in cui Tlbimp.exe genera gli assembly, non è possibile ridestinare un assembly a una versione `mscorlib` diversa. Ad esempio, se si vuole generare un assembly per .NET Framework 2.0, è necessario usare la versione di Tlbimp.exe fornita con .NET Framework 2.0/3.0/3.5 SDK. Per NET Framework 4.x, è necessario usare la versione di Tlbimp.exe fornita con .NET Framework 4.x SDK.

 Quando si importa una libreria dei tipi da un modulo contenente più librerie dei tipi, è possibile aggiungere un ID risorsa a un file di libreria dei tipi. Tlbimp.exe riesce a individuare questo file solo se si trova nella directory corrente o se si specifica il percorso completo. Vedere l'esempio riportato più avanti in questo argomento.  
  
## <a name="examples"></a>Esempi  
 Il comando riportato di seguito genera un assembly con lo stesso nome della libreria dei tipi presente in `myTest.tlb` e con l'estensione .dll.  
  
```console  
tlbimp myTest.tlb
```  
  
 Il comando riportato di seguito genera un assembly denominato `myTest.dll`.  
  
```console  
tlbimp  myTest.tlb  /out:myTest.dll  
```  
  
 Il comando riportato di seguito genera un assembly con lo stesso nome della libreria dei tipi specificata da `MyModule.dll\1` e con estensione dll. `MyModule.dll\1` deve trovarsi nella directory corrente.  
  
```console  
tlbimp MyModule.dll\1  
```  
  
 Il comando riportato di seguito genera un assembly denominato `myTestLib.dll` per la libreria dei tipi `TestLib.dll`. L'opzione **/transform:dispret** trasforma tutti i parametri [out, retval] dei metodi in dispinterfaces nella libreria dei tipi in valori restituiti nella libreria gestita.  
  
```console  
tlbimp TestLib.dll /transform:dispret /out:myTestLib.dll  
```  
  
 La libreria dei tipi `TestLib.dll`, nell'esempio precedente, include un metodo dispinterface denominato `SomeMethod` che restituisce un valore void e presenta un parametro [out, retval]. Il codice riportato di seguito è la firma del metodo della libreria dei tipi di input per `SomeMethod` in `TestLib.dll`.  
  
```cpp  
void SomeMethod([out, retval] VARIANT_BOOL*);  
```  
  
 Se si specifica l'opzione **/transform:dispret**, Tlbimp.exe trasformerà il parametro `[out, retval]` di `SomeMethod`in un valore restituito `bool`. Di seguito è riportata la firma del metodo prodotta da Tlbimp.exe per `SomeMethod` nella libreria gestita `myTestLib.dll` quando viene specificata l'opzione **/transform:dispret**.  
  
```csharp  
bool SomeMethod();  
```  
  
 Se si usa Tlbimp.exe per produrre una libreria gestita per `TestLib.dll` senza specificare **/transform:dispret**, verrà prodotta la firma del metodo riportata di seguito per `SomeMethod` nella libreria gestita `myTestLib.dll`.  
  
```csharp  
void SomeMethod(out bool x);  
```  
  
## <a name="see-also"></a>Vedere anche

- [Strumenti](index.md)
- [Tlbexp.exe (utilità di esportazione della libreria dei tipi)](tlbexp-exe-type-library-exporter.md)
- [Importazione di una libreria dei tipi come assembly](../interop/importing-a-type-library-as-an-assembly.md)
- [Riepilogo della conversione da libreria dei tipi ad assembly](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/k83zzh38(v=vs.100))
- [Ildasm.exe (disassembler IL)](ildasm-exe-il-disassembler.md)
- [Sn.exe (strumento Nome sicuro)](sn-exe-strong-name-tool.md)
- [Assembly con nomi sicuri](../../standard/assembly/strong-named.md)
- [Attributi per l'importazione di librerie dei tipi in assembly di interoperabilità](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/y6a7ak23(v=vs.100))
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
