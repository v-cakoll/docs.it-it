---
title: Winmdexp.exe (Windows Runtime Metadata Export Tool)
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-clr
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords:
- Windows Runtime Metadata Export Tool
- Winmdexp.exe
ms.assetid: d2ce0683-343d-403e-bb8d-209186f7a19d
caps.latest.revision: "16"
author: rpetrusha
ms.author: ronpet
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 723f724663cb7f08814327a04193f96db7f02ed0
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="winmdexpexe-windows-runtime-metadata-export-tool"></a>Winmdexp.exe (Windows Runtime Metadata Export Tool)
Lo strumento di esportazione dei metadati di [!INCLUDE[wrt](../../../includes/wrt-md.md)] (Winmdexp.exe) trasforma un modulo .NET Framework in un file che contiene metadati di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Anche se gli assembly .NET Framework e i file di metadati di [!INCLUDE[wrt](../../../includes/wrt-md.md)] utilizzano lo stesso formato fisico, esistono differenze nel contenuto delle tabelle dei metadati, con la conseguenza che gli assembly .NET Framework non sono automaticamente utilizzabili come componenti di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Il processo di trasformazione di un modulo .NET Framework in un componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)] è denominato *esportazione*. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] e [!INCLUDE[net_v451](../../../includes/net-v451-md.md)] il file di metadati di Windows (.winmd) risultante contiene sia i metadati che l'implementazione.  
  
 Quando si usa il modello **Componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)]**, che si trova in **Windows Store** per C# e Visual Basic in [!INCLUDE[vs_dev12](../../../includes/vs-dev12-md.md)] o in [!INCLUDE[vs_dev11_ext](../../../includes/vs-dev11-ext-md.md)], la destinazione del compilatore è un file con estensione winmdobj. Un successivo passaggio di compilazione chiama Winmdexp.exe per esportare il file con estensione winmdobj in un file con estensione winmd. Questo è il modo consigliato di compilare un componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Utilizzare direttamente Winmdexp.exe quando si desidera un maggiore controllo sul processo di compilazione rispetto a quello offerto da Visual Studio.  
  
 Viene installato automaticamente con Visual Studio. Per eseguire lo strumento, usare il prompt dei comandi per sviluppatori o il prompt dei comandi di Visual Studio in Windows 7. Per altre informazioni, vedere [Prompt dei comandi](../../../docs/framework/tools/developer-command-prompt-for-vs.md).  
  
 Al prompt dei comandi digitare quanto segue:  
  
## <a name="syntax"></a>Sintassi  
  
```  
winmdexp [options] winmdmodule  
```  
  
#### <a name="parameters"></a>Parametri  
  
|Argomento o opzione|Descrizione|  
|------------------------|-----------------|  
|`winmdmodule`|Specifica il modulo (.winmdobj) da esportare. È consentito un solo modulo. Per creare questo modulo, utilizzare l'opzione del compilatore `/target` con destinazione `winmdobj`. Vedere [/target:winmdobj (opzioni del compilatore C#)](~/docs/csharp/language-reference/compiler-options/target-winmdobj-compiler-option.md) o [/target (Visual Basic)](~/docs/visual-basic/reference/command-line-compiler/target.md).|  
|`/docfile:` `docfile`<br /><br /> `/d:` `docfile`|Specifica il file di documentazione XML di output che verrà prodotto da Winmdexp.exe. In [!INCLUDE[net_v45](../../../includes/net-v45-md.md)] il file di output è sostanzialmente lo stesso file di documentazione XML di input.|  
|`/moduledoc:` `docfile`<br /><br /> `/md:` `docfile`|Specifica il nome del file di documentazione XML che il compilatore ha creato con `winmdmodule`.|  
|`/modulepdb:` `symbolfile`<br /><br /> `/mp:` `symbolfile`|Specifica il nome del file del database di programma (PDB) contenente i simboli per `winmdmodule`.|  
|`/nowarn:` `warning`|Non visualizza il numero di avviso specificato. Per *warning*, fornire solo la parte numerica del codice di errore, senza zeri iniziali.|  
|`/out:` `file`<br /><br /> `/o:` `file`|Specifica il nome del file di metadati di Windows (.winmd) di output.|  
|`/pdb:` `symbolfile`<br /><br /> `/p:` `symbolfile`|Specifica il nome del file del database di programma (PDB) di output che conterrà i simboli per il file di metadati di Windows (.winmd) esportato.|  
|`/reference:` `winmd`<br /><br /> `/r:` `winmd`|Specifica un file di metadati (.winmd o assembly) a cui fare riferimento durante l'esportazione. Se si usano gli assembly di riferimento contenuti in "\Programmi (x86)\Reference Assemblies\Microsoft\Framework\\.NETCore\v4.5" ("\Programmi\\..." in computer a 32 bit), includere i riferimenti sia a System.Runtime.dll che a mscorlib.dll.|  
|`/utf8output`|Specifica che la codifica dei messaggi di output deve essere UTF-8.|  
|`/warnaserror+`|Specifica di considerare tutti gli avvisi come errori.|  
|**@** `responsefile`|Specifica un file di risposta (.rsp) contenente le opzioni (e facoltativamente `winmdmodule`). Ogni riga in `responsefile` deve contenere un solo argomento o opzione.|  
  
## <a name="remarks"></a>Note  
 Winmdexp.exe non è progettato per convertire un assembly .NET Framework arbitrario in un file .winmd. Richiede un modulo compilato con l'opzione `/target:winmdobj` e prevede delle restrizioni aggiuntive. La più importante di queste restrizioni è che tutti i tipi esposti nella superficie dell'API dell'assembly devono essere tipi di [!INCLUDE[wrt](../../../includes/wrt-md.md)]. Per altre informazioni, vedere la sezione "Dichiarazioni di tipi nei componenti Windows Runtime" nell'articolo [Creazione di componenti Windows Runtime in C# e Visual Basic in Windows Dev Center](http://go.microsoft.com/fwlink/p/?LinkID=238313).  
  
 Quando si scrive un'app [!INCLUDE[win8_appname_long](../../../includes/win8-appname-long-md.md)] o un componente di [!INCLUDE[wrt](../../../includes/wrt-md.md)] con C# o Visual Basic, .NET Framework fornisce supporto per rendere la programmazione con [!INCLUDE[wrt](../../../includes/wrt-md.md)] più naturale. Questo argomento viene illustrato nell'articolo [Supporto .NET Framework per applicazioni Windows Store e Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md). Nel processo, alcuni tipi di uso comune di [!INCLUDE[wrt](../../../includes/wrt-md.md)] vengono mappati ai tipi .NET Framework. Winmdexp.exe inverte questo processo e produce una superficie API che utilizza i tipi di [!INCLUDE[wrt](../../../includes/wrt-md.md)] corrispondenti. Ad esempio, per i tipi che vengono costruiti dall'interfaccia <xref:System.Collections.Generic.IList%601> viene effettuato il mapping ai tipi costruiti dall'interfaccia [IVector\<T>](http://go.microsoft.com/fwlink/p/?LinkId=251132) di [!INCLUDE[wrt](../../../includes/wrt-md.md)].  
  
## <a name="see-also"></a>Vedere anche  
 [.NET Framework Support for Windows Store Apps and Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (Supporto di .NET Framework per le app di Windows Store e Windows Runtime)  
 [Creazione di componenti Windows Runtime in C# e Visual Basic](http://go.microsoft.com/fwlink/p/?LinkID=238313)  
 [Winmdexp.exe Error Messages](../../../docs/framework/tools/winmdexp-exe-error-messages.md)  
 [Strumenti di compilazione, distribuzione e configurazione (.NET Framework)](http://msdn.microsoft.com/library/b8c921be-6012-4181-b8d4-ab15813fc9a7)
