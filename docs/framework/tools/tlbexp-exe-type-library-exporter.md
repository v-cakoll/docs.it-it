---
title: Tlbexp.exe (utilità di esportazione della libreria dei tipi)
ms.date: 03/30/2017
helpviewer_keywords:
- exporting type library [.NET Framework]
- exporter tool [.NET Framework]
- Tlbexp.exe
- Type Library Exporter
- type libraries [.NET Framework], exporting
ms.assetid: a487d61b-d166-467b-a7ca-d8b52fbff42d
ms.openlocfilehash: 1d2380ff607836b5dc15e7194b90dd3a53d1d2c0
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/15/2020
ms.locfileid: "79180266"
---
# <a name="tlbexpexe-type-library-exporter"></a>Tlbexp.exe (utilità di esportazione della libreria dei tipi)
L'utilità di esportazione della libreria dei tipi genera una libreria di tipi che descrive i tipi definiti in un assembly di Common Language Runtime.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```console  
tlbexp assemblyName [options]  
```  
  
## <a name="parameters"></a>Parametri  
  
|Argomento|Descrizione|  
|--------------|-----------------|  
|*Assemblyname*|Assembly per il quale esportare una libreria dei tipi.|  
  
|Opzione|Descrizione|  
|------------|-----------------|  
|**/asmpath:** *directory*|Specifica il percorso in cui eseguire la ricerca degli assembly. Se si utilizza questa opzione, è necessario specificare in modo esplicito i percorsi in cui eseguire la ricerca degli assembly a cui si fa riferimento, inclusa la directory corrente.<br /><br /> Quando si usa l'opzione **asmpath**, l'utilità di esportazione della libreria dei tipi non cerca un assembly nella Global Assembly Cache (GAC).|  
|**/help**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
|**/names:** *filename*|Specifica la combinazione di maiuscole/minuscole per i nomi di una libreria dei tipi. L'argomento *filename* è un file di testo. Ogni riga del file specifica la combinazione di maiuscole/minuscole di un nome presente nella libreria dei tipi.|  
|**/nologo**|Evita la visualizzazione del messaggio di avvio Microsoft.|  
|**/oldnames**|Forza Tlbexp.exe a esportare i nomi di tipi decorati se si verifica un conflitto tra nomi di tipi. Questo era il comportamento predefinito nelle versioni di .NET Framework precedenti alla 2.0.|  
|**/out:** *file*|Specifica il nome del file della libreria dei tipi da generare. Se si omette questa opzione, verrà generata una libreria dei tipi che avrà lo stesso nome dell'assembly (il nome effettivo dell'assembly, che non deve necessariamente coincidere con quello del file contenente l'assembly) e l'estensione .tlb.|  
|**/silence:** `warningnumber`|Non visualizza l'avviso specificato. Questa opzione non può essere usata con **/silent**.|  
|**/silent**|Evita la visualizzazione dei messaggi di operazione riuscita. Questa opzione non può essere usata con **/silence**.|  
|**/tlbreference:** *typelibraryname*|Forza Tlbexp.exe a risolvere in modo esplicito i riferimenti alla libreria dei tipi senza consultare il Registro di sistema. Se ad esempio l'assembly B fa riferimento all'assembly A, è possibile utilizzare questa opzione per fornire un riferimento esplicito alla libreria dei tipi anziché basarsi sulla libreria dei tipi specificata nel Registro di sistema. Viene eseguito un controllo della versione per assicurare che la versione della libreria dei tipi corrisponda alla versione dell'assembly. In caso contrario, viene generato un errore.<br /><br /> L'opzione **tlbreference** consulta comunque il Registro di sistema se l'attributo <xref:System.Runtime.InteropServices.ComImportAttribute> viene applicato a un'interfaccia che viene successivamente implementata da un altro tipo.|  
|**/tlbrefpath:** *path*|Percorso completo di una libreria dei tipi a cui è stato fatto riferimento.|  
|**/win32 (informazioni in inglese)**|Nella compilazione a 64 bit questa opzione specifica che Tlbexp.exe genera una libreria dei tipi a 32 bit.|  
|**/win64**|Nella compilazione a 32 bit questa opzione specifica che Tlbexp.exe genera una libreria dei tipi a 64 bit.|  
|**/verbose (in inglese)**|Specifica la modalità dettagliata. Visualizza l'elenco di tutti gli assembly a cui si fa riferimento per i quali è necessario generare una libreria dei tipi.|  
|**/?**|Visualizza la sintassi e le opzioni di comando dello strumento.|  
  
> [!NOTE]
> Le opzioni della riga di comando di Tlbexp.exe non sono soggette alla distinzione tra maiuscole e minuscole e per specificarle non è necessario seguire un ordine particolare. Per identificarle in modo univoco, è sufficiente digitare solo una parte dell'opzione. Ad esempio, **/n** equivale a **/nologo** e **/o:** *outfile.tlb* equivale a **/out:** *outfile.tlb*.  
  
## <a name="remarks"></a>Osservazioni  
 Tlbexp.exe consente di generare una libreria dei tipi che contiene le definizioni dei tipi definiti nell'assembly. Le applicazioni come Visual Basic 6.0 possono utilizzare la libreria dei tipi generata per operare un'associazione ai tipi .NET definiti nell'assembly.  
  
> [!IMPORTANT]
> Non è possibile utilizzare Tlbexp.exe per esportare file di metadati Windows (.winmd). L'esportazione di assembly Windows Runtime non è supportata.  
  
 L'intero assembly viene convertito in un'unica operazione. Non è possibile utilizzare Tlbexp.exe per generare informazioni sui tipi per un sottoinsieme dei tipi definiti in un assembly.  
  
 Questo strumento non può essere usato per produrre una libreria dei tipi da un assembly importato mediante l'[utilità di importazione della libreria dei tipi (Tlbimp.exe)](tlbimp-exe-type-library-importer.md). Al contrario, è necessario riferirsi alla libreria dei tipi originale importata con Tlbimp.exe. È possibile esportare una libreria dei tipi da un assembly che fa riferimento agli assembly importati utilizzando Tlbimp.exe. Vedere la sezione degli esempi di seguito.  
  
 Tlbexp.exe colloca le librerie dei tipi generate nella directory di lavoro corrente o nella directory specificata per il file di output. Da un unico assembly possono essere generate più librerie dei tipi.  
  
 Tlbexp.exe genera una libreria dei tipi ma non la registra. Questo comportamento è opposto a quello dello [strumento di registrazione degli assembly (Regasm.exe)](regasm-exe-assembly-registration-tool.md), che effettua sia la generazione che la registrazione delle librerie dei tipi. Per generare e registrare una libreria dei tipi con COM, utilizzare Regasm.exe.  
  
 Se non si specificano né l'opzione `/win32`, né l'opzione `/win64`, verrà generata una libreria dei tipi a 32 o 64 bit corrispondente al tipo di computer, a 32 o a 64 bit, utilizzato per l'esecuzione della compilazione. Ai fini della compilazione incrociata, è possibile utilizzare l'opzione `/win64` su un computer a 32 bit per generare una libreria dei tipi a 64 bit e l'opzione `/win32` su un computer a 64 bit per generare una libreria dei tipi a 32 bit. Nelle librerie dei tipi a 32 bit il valore di <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> viene impostato su <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN32>. Nelle librerie dei tipi a 64 bit il valore di <xref:System.Runtime.InteropServices.ComTypes.SYSKIND> viene impostato su <xref:System.Runtime.InteropServices.ComTypes.SYSKIND.SYS_WIN64>. Tutti i tipi di dati (ad esempio i dati di tipo puntatore quali `IntPtr` e `UIntPtr`) vengono convertiti di conseguenza.  
  
 Se si utilizza l'attributo <xref:System.Runtime.InteropServices.MarshalAsAttribute> per specificare un valore <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArraySubType> di `VT_UNKOWN` o `VT_DISPATCH`, gli eventuali utilizzi successivi del campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> verranno ignorati. Date, ad esempio, le seguenti firme:  
  
```csharp
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_UNKNOWN, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructUnkSafe(){return null;}  
[return:MarshalAs(UnmanagedType.SafeArray, SafeArraySubType=VarEnum.VT_DISPATCH, SafeArrayUserDefinedSubType=typeof(ConsoleKeyInfo))] public Array StructDispSafe(){return null;}  
```  
  
 verrà generata la seguente libreria dei tipi:  
  
```cpp
[id(0x60020004)]  
HRESULT StructUnkSafe([out, retval] SAFEARRAY(IUnknown*)* pRetVal);  
[id(0x60020005)]  
HRESULT StructDispSafe([out, retval] SAFEARRAY(IDispatch*)* pRetVal);  
```  
  
 Si noti che il campo <xref:System.Runtime.InteropServices.MarshalAsAttribute.SafeArrayUserDefinedSubType> viene ignorato.  
  
 Poiché le librerie dei tipi non possono contenere tutte le informazioni presenti negli assembly, può accadere che in Tlbexp.exe vengano ignorati alcuni dati durante il processo di esportazione. Per informazioni sul processo di trasformazione e sull'identificazione dell'origine di tutti i dati emessi in una libreria dei tipi, vedere [Riepilogo della conversione da assembly a libreria dei tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100)).  
  
 L'utilità di esportazione della libreria dei tipi esporta i metodi con parametri <xref:System.TypedReference> di tipo `VARIANT`, anche se l'oggetto <xref:System.TypedReference> non ha significato nel codice non gestito. Quando si esportano metodi con parametri <xref:System.TypedReference>, l'utilità in questione non genera un avviso o un errore e il codice non gestito che utilizza la libreria dei tipi risultante non viene eseguito correttamente.  
  
 L'utilità di esportazione della libreria dei tipi è supportata su Microsoft Windows 2000 e versioni successive.  
  
## <a name="examples"></a>Esempi  
 Il comando che segue genera una libreria dei tipi con lo stesso nome dell'assembly contenuto in `myTest.dll`.  
  
```console  
tlbexp myTest.dll  
```  
  
 Il comando che segue genera una libreria dei tipi con il nome `clipper.tlb`.  
  
```console  
tlbexp myTest.dll /out:clipper.tlb  
```  
  
 Nell'esempio che segue è illustrato come utilizzare Tlbexp.exe per esportare una libreria dei tipi da un assembly che fa riferimento ad assembly importati mediante Tlbimp.exe.  
  
 Utilizzare innanzitutto Tlbimp.exe per importare la libreria dei tipi `myLib.tlb` e salvarla con il nome `myLib.dll`.  
  
```console  
tlbimp myLib.tlb /out:myLib.dll  
```  
  
 Il comando che segue utilizza il compilatore C# per compilare `Sample.dll,` che fa riferimento al file `myLib.dll` creato nell'esempio precedente.  
  
```console  
CSC Sample.cs /reference:myLib.dll /out:Sample.dll  
```  
  
 Il comando che segue genera una libreria dei tipi per `Sample.dll` che fa riferimento a `myLib.dll`.  
  
```console  
tlbexp Sample.dll  
```  
  
## <a name="see-also"></a>Vedere anche

- <xref:System.Runtime.InteropServices.TypeLibExporterFlags>
- [Strumenti](index.md)
- [Regasm.exe (strumento di registrazione di assembly)](regasm-exe-assembly-registration-tool.md)
- [Riepilogo della conversione da assembly a libreria dei tipi](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/xk1120c3(v=vs.100))
- [Tlbimp.exe (utilità di importazione della libreria dei tipi)](tlbimp-exe-type-library-importer.md)
- [Prompt dei comandi](developer-command-prompt-for-vs.md)
