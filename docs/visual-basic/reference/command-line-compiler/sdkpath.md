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
ms.openlocfilehash: bf665082f079901ec45122ce7797090b7519fafe
ms.sourcegitcommit: 9bd8f213b50f0e1a73e03bd1e840c917fbd6d20a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50046799"
---
# <a name="-sdkpath"></a>-sdkpath
Specifica il percorso dei file mscorlib. dll e VisualBasic.  
  
## <a name="syntax"></a>Sintassi  
  
```  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argomenti  
 `path`  
 La directory che contiene le versioni di mscorlib. dll e VisualBasic da utilizzare per la compilazione. Questo percorso non viene verificato fino a quando non viene caricato. Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.  
  
## <a name="remarks"></a>Note  
 Questa opzione indica al compilatore di Visual Basic per caricare il file mscorlib. dll e file VisualBasic da un percorso non predefinito. Il `-sdkpath` opzione è stata progettata per essere usata con [- netcf](../../../visual-basic/reference/command-line-compiler/netcf.md). Il [!INCLUDE[Compact](~/includes/compact-md.md)] Usa diverse versioni di queste librerie di supporto per evitare l'utilizzo di tipi e le funzionalità del linguaggio non trovate nei dispositivi.  
  
> [!NOTE]
>  Il `-sdkpath` opzione non è disponibile all'interno dell'ambiente di sviluppo di Visual Studio, è disponibile solo durante la compilazione dalla riga di comando. Il `-sdkpath` opzione viene impostata quando viene caricato un progetto di Visual Basic dispositivo.  
  
 È possibile specificare che il compilatore esegue la compilazione senza un riferimento alla libreria di Runtime di Visual Basic usando il `-vbruntime` opzione del compilatore. Per altre informazioni, vedere [- /vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente Compila `Myfile.vb` con il [!INCLUDE[Compact](~/includes/compact-md.md)], con le versioni di mscorlib. dll e VisualBasic trovato nella directory di installazione predefinita del [!INCLUDE[Compact](~/includes/compact-md.md)] nell'unità C. In genere, si utilizzerebbe la versione più recente del [!INCLUDE[Compact](~/includes/compact-md.md)].  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vedere anche  
 [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)  
 [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)  
 [-netcf](../../../visual-basic/reference/command-line-compiler/netcf.md)  
 [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
