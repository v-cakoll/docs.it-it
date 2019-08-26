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
ms.sourcegitcommit: 986f836f72ef10876878bd6217174e41464c145a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 08/19/2019
ms.locfileid: "69602569"
---
# <a name="-pdb-c-compiler-options"></a><span data-ttu-id="99ab4-102">-pdb (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="99ab4-102">-pdb (C# Compiler Options)</span></span>
<span data-ttu-id="99ab4-103">L'opzione del compilatore **-pdb** consente di specificare il nome e il percorso del file dei simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="99ab4-103">The **-pdb** compiler option specifies the name and location of the debug symbols file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="99ab4-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="99ab4-104">Syntax</span></span>  
  
```console  
-pdb:filename  
```  
  
## <a name="arguments"></a><span data-ttu-id="99ab4-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="99ab4-105">Arguments</span></span>  
 `filename`  
 <span data-ttu-id="99ab4-106">Nome e percorso del file di simboli di debug.</span><span class="sxs-lookup"><span data-stu-id="99ab4-106">The name and location of the debug symbols file.</span></span>  
  
## <a name="remarks"></a><span data-ttu-id="99ab4-107">Osservazioni</span><span class="sxs-lookup"><span data-stu-id="99ab4-107">Remarks</span></span>  
 <span data-ttu-id="99ab4-108">Quando si specifica [-debug (opzioni del compilatore C#)](./debug-compiler-option.md), il compilatore crea nella stessa directory in cui verrà creato il file di output (con estensione exe o dll) un file con estensione pdb il cui nome è identico a quello del file di output.</span><span class="sxs-lookup"><span data-stu-id="99ab4-108">When you specify [-debug (C# Compiler Options)](./debug-compiler-option.md), the compiler will create a .pdb file in the same directory where the compiler will create the output file (.exe or .dll) with a file name that is the same as the name of the output file.</span></span>  
  
 <span data-ttu-id="99ab4-109">**-pdb** consente di specificare un nome e un percorso non predefiniti per il file con estensione pdb.</span><span class="sxs-lookup"><span data-stu-id="99ab4-109">**-pdb** allows you to specify a non-default file name and location for the .pdb file.</span></span>  
  
 <span data-ttu-id="99ab4-110">Questa opzione del compilatore non può essere impostata nell'ambiente di sviluppo di Visual Studio, né modificata a livello di codice.</span><span class="sxs-lookup"><span data-stu-id="99ab4-110">This compiler option cannot be set in the Visual Studio development environment, nor can it be changed programmatically.</span></span>  
  
## <a name="example"></a><span data-ttu-id="99ab4-111">Esempio</span><span class="sxs-lookup"><span data-stu-id="99ab4-111">Example</span></span>  
 <span data-ttu-id="99ab4-112">Compilare `t.cs` e creare un file con estensione pdb denominato tt.pdb:</span><span class="sxs-lookup"><span data-stu-id="99ab4-112">Compile `t.cs` and create a .pdb file called tt.pdb:</span></span>  
  
```console  
csc -debug -pdb:tt t.cs  
```  
  
## <a name="see-also"></a><span data-ttu-id="99ab4-113">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="99ab4-113">See also</span></span>

- [<span data-ttu-id="99ab4-114">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="99ab4-114">C# Compiler Options</span></span>](./index.md)
- [<span data-ttu-id="99ab4-115">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="99ab4-115">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
