---
title: -pdb (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
ms.openlocfilehash: 3081f4716e8cd858d789db6050e635af941aa05c
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "69602569"
---
# <a name="-pdb-c-compiler-options"></a>-pdb (opzioni del compilatore C#)
L'opzione del compilatore **-pdb** consente di specificare il nome e il percorso del file dei simboli di debug.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a>Argomenti  
 `filename`  
 Nome e percorso del file di simboli di debug.  
  
## <a name="remarks"></a>Osservazioni  
 Quando si specifica [-debug (opzioni del compilatore C#)](./debug-compiler-option.md), il compilatore crea nella stessa directory in cui verrà creato il file di output (con estensione exe o dll) un file con estensione pdb il cui nome è identico a quello del file di output.  
  
 **-pdb** consente di specificare un nome e un percorso non predefiniti per il file con estensione pdb.  
  
 Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.  
  
## <a name="example"></a>Esempio  
 Compilare `t.cs` e creare un file con estensione pdb denominato tt.pdb:  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a>Vedere anche

- [Opzioni del compilatore C](./index.md)
- [Gestione delle proprietà di progetti e soluzioni](/visualstudio/ide/managing-project-and-solution-properties)
