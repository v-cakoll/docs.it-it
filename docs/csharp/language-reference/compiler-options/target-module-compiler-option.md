---
title: -target:module (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
f1_keywords: /target:module
helpviewer_keywords:
- -target compiler options [C#], /target:module
- target compiler options [C#], /target:module
- /target compiler options [C#], /target:module
ms.assetid: 9af1e4fa-c749-44e7-ae58-90a3d05d4e72
caps.latest.revision: "11"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 679d659b2806fb875f908cee840a62278c99096f
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
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
 [-target (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/target-compiler-option.md)  
 [Opzioni del compilatore C#](../../../csharp/language-reference/compiler-options/index.md)
