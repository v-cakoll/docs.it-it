---
title: -libpath
ms.date: 03/10/2018
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
ms.openlocfilehash: 8f4e415576562885c9edbd3d2dddbe2a271e9923
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005461"
---
# <a name="-libpath"></a><span data-ttu-id="30e03-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="30e03-102">-libpath</span></span>
<span data-ttu-id="30e03-103">Specifica il percorso degli assembly a cui si fa riferimento.</span><span class="sxs-lookup"><span data-stu-id="30e03-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="30e03-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="30e03-104">Syntax</span></span>  
  
```console  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="30e03-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="30e03-105">Arguments</span></span>  
  
|<span data-ttu-id="30e03-106">Nome</span><span class="sxs-lookup"><span data-stu-id="30e03-106">Term</span></span>|<span data-ttu-id="30e03-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="30e03-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="30e03-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="30e03-108">Required.</span></span> <span data-ttu-id="30e03-109">Elenco delimitato da punti e virgola di directory per il compilatore da cercare se un assembly a cui si fa riferimento non viene trovato nella directory di lavoro corrente (la directory da cui si richiama il compilatore) o nella directory di sistema del Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="30e03-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="30e03-110">Se il nome della directory contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="30e03-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="30e03-111">Note</span><span class="sxs-lookup"><span data-stu-id="30e03-111">Remarks</span></span>  
 <span data-ttu-id="30e03-112">L'opzione `-libpath` specifica il percorso degli assembly a cui fa riferimento l'opzione [-Reference](../../../visual-basic/reference/command-line-compiler/reference.md) .</span><span class="sxs-lookup"><span data-stu-id="30e03-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="30e03-113">La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="30e03-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1. <span data-ttu-id="30e03-114">Directory di lavoro corrente,</span><span class="sxs-lookup"><span data-stu-id="30e03-114">Current working directory.</span></span> <span data-ttu-id="30e03-115">ovvero la directory da cui viene chiamato il compilatore.</span><span class="sxs-lookup"><span data-stu-id="30e03-115">This is the directory from which the compiler is invoked.</span></span>  
  
2. <span data-ttu-id="30e03-116">Directory di sistema di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="30e03-116">The common language runtime system directory.</span></span>  
  
3. <span data-ttu-id="30e03-117">Directory specificate da `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="30e03-117">Directories specified by `/libpath`.</span></span>  
  
4. <span data-ttu-id="30e03-118">Directory specificate dalla variabile di ambiente LIB.</span><span class="sxs-lookup"><span data-stu-id="30e03-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="30e03-119">L'opzione `-libpath` è additiva; la specifica di più di una volta viene accodata a qualsiasi valore precedente.</span><span class="sxs-lookup"><span data-stu-id="30e03-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="30e03-120">Utilizzare `-reference` per specificare un riferimento a un assembly.</span><span class="sxs-lookup"><span data-stu-id="30e03-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="30e03-121">Per impostare/LIBPATH in Visual Studio Integrated Development Environment</span><span class="sxs-lookup"><span data-stu-id="30e03-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="30e03-122">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="30e03-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="30e03-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="30e03-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="30e03-124">2.  Fare clic sulla scheda **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="30e03-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="30e03-125">3.  Fare clic sul pulsante **Percorsi riferimento...** .</span><span class="sxs-lookup"><span data-stu-id="30e03-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="30e03-126">4.  Nella finestra di dialogo **Percorsi riferimento** immettere il nome della directory nella casella **cartella:** .</span><span class="sxs-lookup"><span data-stu-id="30e03-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="30e03-127">5.  Fare clic su **Aggiungi cartella**.</span><span class="sxs-lookup"><span data-stu-id="30e03-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="30e03-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="30e03-128">Example</span></span>  
 <span data-ttu-id="30e03-129">Il codice seguente compila `T2.vb` per creare un file con estensione exe.</span><span class="sxs-lookup"><span data-stu-id="30e03-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="30e03-130">Il compilatore cerca nella directory di lavoro, nella directory radice dell'unità C: e nella nuova directory degli assembly dell'unità C: per i riferimenti all'assembly.</span><span class="sxs-lookup"><span data-stu-id="30e03-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="30e03-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="30e03-131">See also</span></span>

- [<span data-ttu-id="30e03-132">Assembly in .NET</span><span class="sxs-lookup"><span data-stu-id="30e03-132">Assemblies in .NET</span></span>](../../../standard/assembly/index.md)
- [<span data-ttu-id="30e03-133">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="30e03-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)
- [<span data-ttu-id="30e03-134">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="30e03-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
