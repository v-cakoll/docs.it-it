---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: dff7e0c3eb696b9b18f4c4e59240a26c1cb9782c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84408549"
---
# <a name="-libpath"></a><span data-ttu-id="e2ace-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="e2ace-102">-libpath</span></span>
<span data-ttu-id="e2ace-103">Specifica il percorso degli assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="e2ace-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="e2ace-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="e2ace-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="e2ace-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="e2ace-105">Arguments</span></span>  
  
|<span data-ttu-id="e2ace-106">Termine</span><span class="sxs-lookup"><span data-stu-id="e2ace-106">Term</span></span>|<span data-ttu-id="e2ace-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="e2ace-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="e2ace-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="e2ace-108">Required.</span></span> <span data-ttu-id="e2ace-109">Elenco delimitato da punti e virgola di directory per il compilatore da cercare se un assembly a cui si fa riferimento non viene trovato nella directory di lavoro corrente (la directory da cui si richiama il compilatore) o nella directory di sistema del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e2ace-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="e2ace-110">Se il nome della directory contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="e2ace-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="e2ace-111">Commenti</span><span class="sxs-lookup"><span data-stu-id="e2ace-111">Remarks</span></span>  
 <span data-ttu-id="e2ace-112">L' `-libpath` opzione specifica il percorso degli assembly a cui fa riferimento l'opzione [-Reference](reference.md) .</span><span class="sxs-lookup"><span data-stu-id="e2ace-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](reference.md) option.</span></span>  
  
 <span data-ttu-id="e2ace-113">La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="e2ace-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="e2ace-114">Directory di lavoro corrente,</span><span class="sxs-lookup"><span data-stu-id="e2ace-114">Current working directory.</span></span> <span data-ttu-id="e2ace-115">ovvero la directory da cui viene chiamato il compilatore.</span><span class="sxs-lookup"><span data-stu-id="e2ace-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="e2ace-116">Directory di sistema di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="e2ace-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="e2ace-117">Directory specificate da `-libpath` .</span><span class="sxs-lookup"><span data-stu-id="e2ace-117">Directories specified by `-libpath`.</span></span>  
  
4. <span data-ttu-id="e2ace-118">Directory specificate dalla variabile di ambiente LIB.</span><span class="sxs-lookup"><span data-stu-id="e2ace-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="e2ace-119">L' `-libpath` opzione è additiva, che viene specificata più di una volta in aggiunta a qualsiasi valore precedente.</span><span class="sxs-lookup"><span data-stu-id="e2ace-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="e2ace-120">Usare `-reference` per specificare un riferimento a un assembly.</span><span class="sxs-lookup"><span data-stu-id="e2ace-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="e2ace-121">Per impostare-LIBPATH in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="e2ace-121">To set -libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="e2ace-122">1. è stato selezionato un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="e2ace-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="e2ace-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="e2ace-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="e2ace-124">2. fare clic sulla scheda **riferimenti** .</span><span class="sxs-lookup"><span data-stu-id="e2ace-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="e2ace-125">3. fare clic sul pulsante **Percorsi riferimento...** .</span><span class="sxs-lookup"><span data-stu-id="e2ace-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="e2ace-126">4. nella finestra di dialogo **Percorsi riferimento** immettere il nome della directory nella casella **cartella:** .</span><span class="sxs-lookup"><span data-stu-id="e2ace-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="e2ace-127">5. fare clic su **Aggiungi cartella**.</span><span class="sxs-lookup"><span data-stu-id="e2ace-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="e2ace-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="e2ace-128">Example</span></span>  
 <span data-ttu-id="e2ace-129">Il codice seguente esegue la compilazione `T2.vb` per creare un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="e2ace-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="e2ace-130">Il compilatore cerca nella directory di lavoro, nella directory radice dell'unità C: e nella nuova directory degli assembly dell'unità C: per i riferimenti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="e2ace-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="e2ace-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e2ace-131">See also</span></span>

- [<span data-ttu-id="e2ace-132">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="e2ace-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="e2ace-133">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e2ace-133">Visual Basic Command-Line Compiler</span></span>](index.md)
- [<span data-ttu-id="e2ace-134">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="e2ace-134">Sample Compilation Command Lines</span></span>](sample-compilation-command-lines.md)
