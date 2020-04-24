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
ms.openlocfilehash: 46cec7ac3cb78c4fc97e299535f9085eff6daeff
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004686"
---
# <a name="-sdkpath"></a>-sdkpath
Specifica il percorso dei file mscorlib. dll e Microsoft. VisualBasic. dll.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-sdkpath:path  
```  
  
## <a name="arguments"></a>Argomenti  
 `path`  
 Directory contenente le versioni di mscorlib. dll e Microsoft. VisualBasic. dll da utilizzare per la compilazione. Questo percorso non viene verificato fino a quando non viene caricato. Racchiudere il nome della directory tra virgolette ("") se contiene uno spazio.  
  
## <a name="remarks"></a>Osservazioni  
 Questa opzione indica al compilatore Visual Basic di caricare i file mscorlib. dll e Microsoft. VisualBasic. dll da un percorso non predefinito. L' `-sdkpath` opzione è stata progettata per essere utilizzata con [-netcf (](../../../visual-basic/reference/command-line-compiler/netcf.md). Il .NET Compact Framework utilizza versioni diverse di queste librerie di supporto per evitare l'utilizzo di tipi e funzionalità del linguaggio non disponibili nei dispositivi.  
  
> [!NOTE]
> L' `-sdkpath` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando. L' `-sdkpath` opzione viene impostata quando viene caricato un progetto Visual Basic dispositivo.  
  
 È possibile specificare che il compilatore deve eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic usando `-vbruntime` l'opzione del compilatore. Per ulteriori informazioni, vedere [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato `Myfile.vb` con il .NET Compact Framework, usando le versioni di mscorlib. dll e Microsoft. VisualBasic. dll disponibili nella directory di installazione predefinita del .NET Compact Framework nell'unità C. In genere, si utilizzerà la versione più recente del .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vedi anche

- [Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md)
- [Esempi di righe di comando di compilazione](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
- [-netcf (](../../../visual-basic/reference/command-line-compiler/netcf.md)
- [-vbruntime](../../../visual-basic/reference/command-line-compiler/vbruntime.md)
