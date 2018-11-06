---
title: -pathmap (opzioni del compilatore C#)
ms.date: 05/16/2018
f1_keywords:
- /pathmap
helpviewer_keywords:
- -pathmap compiler option [C#]
- pathmap compiler option [C#]
- /pathmap compiler option [C#]
ms.openlocfilehash: abcc67a16e257a15599431a8fefe7753e6d52549
ms.sourcegitcommit: c93fd5139f9efcf6db514e3474301738a6d1d649
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 10/27/2018
ms.locfileid: "50190320"
---
# <a name="-pathmap-c-compiler-options"></a><span data-ttu-id="51501-102">-pathmap (opzioni del compilatore C#)</span><span class="sxs-lookup"><span data-stu-id="51501-102">-pathmap (C# Compiler Options)</span></span>

<span data-ttu-id="51501-103">L'opzione del compilatore **-pathmap** specifica come eseguire il mapping di percorsi fisici ai nomi di percorso di origine restituiti dal compilatore.</span><span class="sxs-lookup"><span data-stu-id="51501-103">The **-pathmap** compiler option specifies how to map physical paths to source path names output by the compiler.</span></span>

## <a name="syntax"></a><span data-ttu-id="51501-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="51501-104">Syntax</span></span>

```console
-pathmap:path1=sourcePath1,path2=sourcePath2
```

## <a name="arguments"></a><span data-ttu-id="51501-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="51501-105">Arguments</span></span>

 <span data-ttu-id="51501-106">`path1` Percorso completo per i file di origine nell'ambiente corrente</span><span class="sxs-lookup"><span data-stu-id="51501-106">`path1` The full path to the source files in the current environment</span></span>

 <span data-ttu-id="51501-107">`sourcePath1` Percorso di origine con cui sostituire `path1` in tutti i file di output.</span><span class="sxs-lookup"><span data-stu-id="51501-107">`sourcePath1` The source path substituted for `path1` in any output files.</span></span>

<span data-ttu-id="51501-108">Per specificare più percorsi di origine mappati, separarli con una virgola.</span><span class="sxs-lookup"><span data-stu-id="51501-108">To specify multiple mapped source paths, separate each with a comma.</span></span>

## <a name="remarks"></a><span data-ttu-id="51501-109">Note</span><span class="sxs-lookup"><span data-stu-id="51501-109">Remarks</span></span>

<span data-ttu-id="51501-110">Il compilatore scrive il percorso di origine nell'output per i motivi seguenti:</span><span class="sxs-lookup"><span data-stu-id="51501-110">The compiler writes the source path into its output for the following reasons:</span></span>

1. <span data-ttu-id="51501-111">Il percorso di origine viene sostituito per un argomento quando si applica <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> a un parametro facoltativo.</span><span class="sxs-lookup"><span data-stu-id="51501-111">The source path is substituted for an argument when the <xref:System.Runtime.CompilerServices.CallerFilePathAttribute> is applied to an optional parameter.</span></span>
1. <span data-ttu-id="51501-112">Il percorso di origine è incorporato in un file PDB.</span><span class="sxs-lookup"><span data-stu-id="51501-112">The source path is embedded in a PDB file.</span></span>
1. <span data-ttu-id="51501-113">Il percorso del file PDB è incorporato in un file PE (eseguibile portabile).</span><span class="sxs-lookup"><span data-stu-id="51501-113">The path of the PDB file is embedded into a PE (portable executable) file.</span></span>

<span data-ttu-id="51501-114">Questa opzione esegue il mapping di ogni percorso fisico nel computer in cui viene eseguito il compilatore in un percorso corrispondente che deve essere scritto nei file di output.</span><span class="sxs-lookup"><span data-stu-id="51501-114">This option maps each physical path on the machine where the compiler runs to a corresponding path that should be written in the output files.</span></span>

## <a name="example"></a><span data-ttu-id="51501-115">Esempio</span><span class="sxs-lookup"><span data-stu-id="51501-115">Example</span></span>

<span data-ttu-id="51501-116">Compilare `t.cs` nella directory **c:\\work\\tests** ed eseguire il mapping di tale directory a **\publish** nell'output:</span><span class="sxs-lookup"><span data-stu-id="51501-116">Compile `t.cs` in the directory **C:\\work\\tests** and map that directory to **\publish** in the output:</span></span>

```console
csc -pathmap:C:\work\tests=\publish t.cs
```

## <a name="see-also"></a><span data-ttu-id="51501-117">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51501-117">See also</span></span>

- [<span data-ttu-id="51501-118">Opzioni del compilatore C#</span><span class="sxs-lookup"><span data-stu-id="51501-118">C# Compiler Options</span></span>](../../../csharp/language-reference/compiler-options/index.md)  
- [<span data-ttu-id="51501-119">Gestione delle proprietà di progetti e soluzioni</span><span class="sxs-lookup"><span data-stu-id="51501-119">Managing Project and Solution Properties</span></span>](/visualstudio/ide/managing-project-and-solution-properties)
