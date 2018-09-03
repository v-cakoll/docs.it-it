---
title: -target:module (opzioni del compilatore C#)
ms.date: 07/20/2015
f1_keywords:
- /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
ms.openlocfilehash: 7cc0e48a7a4a3ec3f28c89e80fadf6aa7e1130f2
ms.sourcegitcommit: efff8f331fd9467f093f8ab8d23a203d6ecb5b60
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 09/02/2018
ms.locfileid: "43393126"
---
# <a name="-targetmodule-c-compiler-options"></a>-target:module (opzioni del compilatore C#)
Questa opzione indica al compilatore di non generare un manifesto dell'assembly.  
  
## <a name="syntax"></a>Sintassi  
  
```console  
-target:module  
```  
  
## <a name="remarks"></a>Note  
 Per impostazione predefinita, l'estensione del file di output creato eseguendo la compilazione con questa opzione sarà netmodule.  
  
 Un file che non dispone di un manifesto dell'assembly non può essere caricato da Common Language Runtime di .NET Framework. È tuttavia possibile incorporare un file di questo tipo nel manifesto di un assembly tramite [-addmodule](../../../csharp/language-reference/compiler-options/addmodule-compiler-option.md).  
  
 Se viene creato più di un modulo in un'unica compilazione, i tipi [internal](../../../csharp/language-reference/keywords/internal.md) in un modulo saranno disponibili per gli altri moduli nella compilazione. Se il codice di un modulo fa riferimento a tipi `internal` in un altro modulo, è necessario incorporare entrambi i moduli in un manifesto dell'assembly tramite **-addmodule**.  
  
 La creazione di un modulo non è supportata nell'ambiente di sviluppo di Visual Studio.  
  
 Per informazioni su come impostare questa opzione del compilatore a livello di codice, vedere <xref:VSLangProj80.ProjectProperties3.OutputType%2A>.  
  
## <a name="example"></a>Esempio  
 Compilare in `in.cs` creando in `in.netmodule`:  
  
```console  
csc -target:module in.cs  
```  
  
## <a name="see-also"></a>Vedere anche  

- [-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
- [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
