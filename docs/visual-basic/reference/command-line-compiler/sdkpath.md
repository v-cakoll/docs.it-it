---
title: -sdkpath
ms.date: 07/20/2015
f1_keywords:
- sdkpath
- -sdkpath
helpviewer_keywords:
- -sdkpath compiler option [Visual Basic]
- /sdkpath compiler option [Visual Basic]
- sdkpath compiler option [Visual Basic]
ms.assetid: fec8a3f1-b791-4a37-8af7-344859f8212d
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 162c7d58350c381ec667e8a4cd11c03e83fcdf44
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="-sdkpath"></a>-sdkpath
Specifica il percorso dei file mscorlib. dll e VisualBasic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argomenti  
 `path`  
 La directory che contiene le versioni di mscorlib. dll e VisualBasic da utilizzare per la compilazione. Questo percorso non è stato verificato finché viene caricato. Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.  
  
## <a name="remarks"></a>Note  
 Questa opzione indica al compilatore di Visual Basic per caricare il file mscorlib. dll e file VisualBasic da un percorso non predefinito. Il `-sdkpath` opzione è stata progettata per essere utilizzato con [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). Il [!INCLUDE[Compact](~/includes/compact-md.md)] Usa diverse versioni di queste librerie di supporto per evitare l'utilizzo di tipi e le funzionalità del linguaggio non trovate nei dispositivi.  
  
> [!NOTE]
>  Il `-sdkpath` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio; è disponibile solo durante la compilazione dalla riga di comando. Il `-sdkpath` opzione viene impostata quando viene caricato un progetto di dispositivo di Visual Basic.  
  
 È possibile specificare che il compilatore deve compilare senza un riferimento alla libreria di Runtime di Visual Basic utilizzando il `-vbruntime` l'opzione del compilatore. Per altre informazioni, vedere [- /vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], usando le versioni dei file Mscorlib.dll e Microsoft.VisualBasic.dll trovato nella directory di installazione predefinita di [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C. In genere, si utilizzerà la versione più recente di [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
