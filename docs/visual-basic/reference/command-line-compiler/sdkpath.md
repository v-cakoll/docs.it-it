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
ms.openlocfilehash: 85aba17b330af1b25b39f462844bc1a4856a448a
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403109"
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
  
## <a name="remarks"></a>Commenti  
 Questa opzione indica al compilatore Visual Basic di caricare i file mscorlib. dll e Microsoft. VisualBasic. dll da un percorso non predefinito. L' `-sdkpath` opzione è stata progettata per essere utilizzata con [-netcf (](netcf.md). Il .NET Compact Framework utilizza versioni diverse di queste librerie di supporto per evitare l'utilizzo di tipi e funzionalità del linguaggio non disponibili nei dispositivi.  
  
> [!NOTE]
> L' `-sdkpath` opzione non è disponibile nell'ambiente di sviluppo di Visual Studio. è disponibile solo quando si esegue la compilazione dalla riga di comando. L' `-sdkpath` opzione viene impostata quando viene caricato un progetto Visual Basic dispositivo.  
  
 È possibile specificare che il compilatore deve eseguire la compilazione senza un riferimento alla libreria di runtime Visual Basic usando l' `-vbruntime` opzione del compilatore. Per ulteriori informazioni, vedere [-vbruntime](vbruntime.md).  
  
## <a name="example"></a>Esempio  
 Il codice seguente viene compilato `Myfile.vb` con il .NET Compact Framework, usando le versioni di mscorlib. dll e Microsoft. VisualBasic. dll disponibili nella directory di installazione predefinita del .NET Compact Framework nell'unità C. In genere, si utilizzerà la versione più recente del .NET Compact Framework.  
  
```console
vbc -netcf -sdkpath:"c:\Program Files\Microsoft Visual Studio .NET 2003\CompactFrameworkSDK\v1.0.5000\Windows CE " myfile.vb  
```  
  
## <a name="see-also"></a>Vedere anche

- [Compilatore della riga di comando di Visual Basic](index.md)
- [Esempi di righe di comando di compilazione](sample-compilation-command-lines.md)
- [-netcf](netcf.md)
- [-vbruntime](vbruntime.md)
