---
title: -pdb (opzioni del compilatore C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
f1_keywords:
- /pdb
helpviewer_keywords:
- -pdb compiler option [C#]
- pdb compiler option [C#]
- /pdb compiler option [C#]
ms.assetid: e9d0f96a-5b75-45d6-9765-92538dd5f823
caps.latest.revision: 
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: 7528283765c2b6f4a9d5e84015526a95938a6281
ms.sourcegitcommit: c0dd436f6f8f44dc80dc43b07f6841a00b74b23f
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 01/19/2018
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="16b23-102">-pdb (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="16b23-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="16b23-103">L'opzione del compilatore **-pdb** consente di specificare il nome e il percorso del file dei simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="16b23-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="16b23-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="16b23-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="16b23-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="16b23-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="16b23-106">Nome e percorso del file di simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="16b23-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="16b23-107">Note</span><span class="sxs-lookup"><span data-stu-id="16b23-107">Remarks</span></span>  
 <span data-ttu-id="16b23-108">Quando si specifica [-debug (opzioni del compilatore C#)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), il compilatore crea nella stessa directory in cui verrà creato il file di output (con estensione exe o dll) un file con estensione pdb il cui nome è identico a quello del file di output.</span><span class="sxs-lookup"><span data-stu-id="16b23-108">When you specify [-debug (C# Compiler Options)](../../../csharp/language-reference/compiler-options/debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="16b23-109">**-pdb** consente di specificare un nome e un percorso non predefiniti per il file con estensione pdb.</span><span class="sxs-lookup"><span data-stu-id="16b23-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="16b23-110">Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="16b23-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="16b23-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="16b23-111">Example</span></span>  
 <span data-ttu-id="16b23-112">Compilare `t.cs` e creare un file con estensione pdb denominato tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="16b23-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="16b23-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="16b23-113">See Also</span></span>  
 [<span data-ttu-id="16b23-114">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="16b23-114">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
 [<span data-ttu-id="16b23-115">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="16b23-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
