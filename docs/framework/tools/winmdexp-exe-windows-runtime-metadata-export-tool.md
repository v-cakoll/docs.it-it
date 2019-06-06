---
title: Winmdexp.exe (Windows Runtime Metadata Export Tool)
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Runtime Metadata Export Tool
- Winmdexp.exe
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: a00828eba91e4fea41e8b6a6da8953fc399387e3
ms.sourcegitcommit: 4735bb7741555bcb870d7b42964d3774f4897a6e
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/30/2019
ms.locfileid: "66378500"
---
# <a name="winmdexpexe-windows-runtime-metadata-export-tool"></a>Winmdexp.exe (Windows Runtime Metadata Export Tool)
Lo strumento di esportazione dei metadati di [!INCLUDE[wrt](../../../includes/wrt-md.md)] (Winmdexp.exe) trasforma un modulo .NET Framework in un file che contiene metadati di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Anche se gli assembly .NET Framework e i file di metadati di [!INCLUDE[wrt](../../../includes/wrt-md.md)] utilizzano lo stesso formato fisico, esistono differenze nel contenuto delle tabelle dei metadati, con la conseguenza che gli assembly .NET Framework non sono automaticamente utilizzabili come componenti di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Il processo di trasformazione di un modulo .NET Framework in un componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)] è denominato *esportazione*. In .NET Framework 4.5 e .NET Framework 4.5.1 il file di metadati di Windows risultante con estensione winmd contiene sia i metadati che l'implementazione.  
  
 Quando si usa il modello **Componente [!INCLUDE[wrt](../../../includes/wrt-md.md)]** , disponibile in **Windows Store** per C# e Visual Basic in Visual Studio 2013 o Visual Studio 2012, la destinazione del compilatore è un file con estensione winmdobj. Un successivo passaggio di compilazione chiama Winmdexp.exe per esportare il file con estensione winmdobj in un file con estensione winmd. Questo è il modo consigliato di compilare un componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Utilizzare direttamente Winmdexp.exe quando si desidera un maggiore controllo sul processo di compilazione rispetto a quello offerto da Visual Studio.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il Prompt dei comandi per gli sviluppatori per Visual Studio (o il prompt dei comandi di Visual Studio in Windows 7). Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
winmdexp [options] winmdmodule  
```  
  
## <a name="parameters"></a>Parametri  
  
|Argomento o opzione|Description|  
|------------------------|-----------------|  
|`winmdmodule`|Specifica il modulo (.winmdobj) da esportare. È consentito un solo modulo. Per creare questo modulo, utilizzare l'opzione del compilatore `/target` con destinazione `winmdobj`. Vedere [/target:winmdobj (opzioni del compilatore C#)](~/docs/csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md) o [/target (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/target.md).|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Specifica il file di documentazione XML di output che verrà prodotto da Winmdexp.exe. In .NET Framework 4.5 il file di output è sostanzialmente lo stesso file di documentazione XML di input.|  
|`/moduledoc:` `docfile`<br /><br /> `/md:` `docfile`|Specifica il nome del file di documentazione XML che il compilatore ha creato con `winmdmodule`.|  
|`/modulepdb:` `symbolfile`<br /><br /> `/mp:` `symbolfile`|Specifica il nome del file del database di programma (PDB) contenente i simboli per `winmdmodule`.|  
|`/nowarn:` `warning`|Non visualizza il numero di avviso specificato. Per *warning*, fornire solo la parte numerica del codice di errore, senza zeri iniziali.|  
|`/out:` `file`<br /><br /> `/o:` `file`|Specifica il nome del file di metadati di Windows (.winmd) di output.|  
|`/pdb:` `symbolfile`<br /><br /> `/p:` `symbolfile`|Specifica il nome del file del database di programma (PDB) di output che conterrà i simboli per il file di metadati di Windows (.winmd) esportato.|  
|`/reference:` `winmd`<br /><br /> `/r:` `winmd`|Specifica un file di metadati (.winmd o assembly) a cui fare riferimento durante l'esportazione. Se si usano gli assembly di riferimento contenuti in "\Programmi (x86)\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5" ("\Programmi\\..." in computer a 32 bit), includere i riferimenti sia a System.Runtime.dll che a mscorlib.dll.|  
|`/utf8output`|Specifica che la codifica dei messaggi di output deve essere UTF-8.|  
|`/warnaserror+`|Specifica di considerare tutti gli avvisi come errori.|  
|**@** `responsefile`|Specifica un file di risposta (.rsp) contenente le opzioni (e facoltativamente `winmdmodule`). Ogni riga in `responsefile` deve contenere un solo argomento o opzione.|  
  
## <a name="remarks"></a>Osservazioni  
 Winmdexp.exe non è progettato per convertire un assembly .NET Framework arbitrario in un file .winmd. Richiede un modulo compilato con l'opzione `/target:winmdobj` e prevede delle restrizioni aggiuntive. La più importante di queste restrizioni è che tutti i tipi esposti nella superficie dell'API dell'assembly devono essere tipi di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Per altre informazioni, vedere la sezione "Dichiarazioni di tipi nei componenti Windows Runtime" nell'articolo [Creazione di componenti Windows Runtime in C# e Visual Basic in Windows Dev Center](https://go.microsoft.com/fwlink/p/?LinkID=238313).  
  
 Quando si scrive un'app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o un componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)] con C# o Visual Basic, .NET Framework fornisce supporto per rendere la programmazione con [!INCLUDE[wrt](../../../includes/wrt-md.md)] più naturale. Questo argomento viene illustrato nell'articolo [Supporto .NET Framework per applicazioni Windows Store e Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md). Nel processo, alcuni tipi di uso comune di [!INCLUDE[wrt](../../../includes/wrt-md.md)] vengono mappati ai tipi .NET Framework. Winmdexp.exe inverte questo processo e produce una superficie API che utilizza i tipi di [!INCLUDE[wrt](../../../includes/wrt-md.md)] corrispondenti. Ad esempio, per i tipi che vengono costruiti dall'interfaccia <xref:System.Collections.Generic.IList%601> viene effettuato il mapping ai tipi costruiti dall'interfaccia [IVector\<T>](https://go.microsoft.com/fwlink/p/?LinkId=251132) di [!INCLUDE[wrt](../../../includes/wrt-md.md)].  
  
## <a name="see-also"></a>Vedere anche

- [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)
- [Creazione di componenti Windows Runtime in C# e Visual Basic](https://go.microsoft.com/fwlink/p/?LinkID=238313)
- [Winmdexp.exe Error Messages](../../../docs/framework/tools/winmdexp-exe-error-messages.md)
- [Strumenti di compilazione, distribuzione e configurazione (.NET Framework)](https://docs.microsoft.com/previous-versions/dotnet/netframework-4.0/dd233108(v=vs.100))
