---
title: -libpath
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- libpath compiler option [Visual Basic]
- /libpath compiler option [Visual Basic]
- -libpath compiler option [Visual Basic]
ms.assetid: 5f1c26c9-3455-4e89-bdf3-b12d6c2e655b
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: cff59d9b406045b4522d3a7d6e85528513214635
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-libpath"></a><span data-ttu-id="a9979-102">-libpath</span><span class="sxs-lookup"><span data-stu-id="a9979-102">-libpath</span></span>
<span data-ttu-id="a9979-103">Specifica il percorso degli assembly di riferimento.</span><span class="sxs-lookup"><span data-stu-id="a9979-103">Specifies the location of referenced assemblies.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="a9979-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="a9979-104">Syntax</span></span>  
  
```  
-libpath:dirList  
```  
  
## <a name="arguments"></a><span data-ttu-id="a9979-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="a9979-105">Arguments</span></span>  
  
|<span data-ttu-id="a9979-106">Termine</span><span class="sxs-lookup"><span data-stu-id="a9979-106">Term</span></span>|<span data-ttu-id="a9979-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="a9979-107">Definition</span></span>|  
|---|---|  
|`dirList`|<span data-ttu-id="a9979-108">Obbligatorio.</span><span class="sxs-lookup"><span data-stu-id="a9979-108">Required.</span></span> <span data-ttu-id="a9979-109">Elenco delimitato da punto e virgola di directory per il compilatore la ricerca se un assembly di riferimento non trova in una directory di lavoro corrente (la directory da cui si richiama il compilatore) o la directory di sistema di common language runtime.</span><span class="sxs-lookup"><span data-stu-id="a9979-109">Semicolon-delimited list of directories for the compiler to look in if a referenced assembly is not found in either the current working directory (the directory from which you are invoking the compiler) or the common language runtime's system directory.</span></span> <span data-ttu-id="a9979-110">Se il nome della directory contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="a9979-110">If the directory name contains a space, enclose the name in quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="a9979-111">Note</span><span class="sxs-lookup"><span data-stu-id="a9979-111">Remarks</span></span>  
 <span data-ttu-id="a9979-112">Il `-libpath` opzione consente di specificare la posizione degli assembly a cui fanno riferimento le [-riferimento](../../../visual-basic/reference/command-line-compiler/reference.md) opzione.</span><span class="sxs-lookup"><span data-stu-id="a9979-112">The `-libpath` option specifies the location of assemblies referenced by the [-reference](../../../visual-basic/reference/command-line-compiler/reference.md) option.</span></span>  
  
 <span data-ttu-id="a9979-113">La ricerca dei riferimenti non completi agli assembly viene operata nell'ordine seguente:</span><span class="sxs-lookup"><span data-stu-id="a9979-113">The compiler searches for assembly references that are not fully qualified in the following order:</span></span>  
  
1.  <span data-ttu-id="a9979-114">Directory di lavoro corrente,</span><span class="sxs-lookup"><span data-stu-id="a9979-114">Current working directory.</span></span> <span data-ttu-id="a9979-115">ovvero la directory da cui viene chiamato il compilatore.</span><span class="sxs-lookup"><span data-stu-id="a9979-115">This is the directory from which the compiler is invoked.</span></span>  
  
2.  <span data-ttu-id="a9979-116">Directory di sistema di Common Language Runtime.</span><span class="sxs-lookup"><span data-stu-id="a9979-116">The common language runtime system directory.</span></span>  
  
3.  <span data-ttu-id="a9979-117">Directory specificate dalle `/libpath`.</span><span class="sxs-lookup"><span data-stu-id="a9979-117">Directories specified by `/libpath`.</span></span>  
  
4.  <span data-ttu-id="a9979-118">Directory specificate dalla variabile di ambiente LIB.</span><span class="sxs-lookup"><span data-stu-id="a9979-118">Directories specified by the LIB environment variable.</span></span>  
  
 <span data-ttu-id="a9979-119">Il `-libpath` opzione si sommano tra loro; specificando che più di una volta aggiunto a eventuali valori precedenti.</span><span class="sxs-lookup"><span data-stu-id="a9979-119">The `-libpath` option is additive; specifying it more than once appends to any prior values.</span></span>  
  
 <span data-ttu-id="a9979-120">Utilizzare `-reference` per specificare un riferimento all'assembly.</span><span class="sxs-lookup"><span data-stu-id="a9979-120">Use `-reference` to specify an assembly reference.</span></span>  
  
|<span data-ttu-id="a9979-121">Per impostare /libpath in Visual Studio ambiente di sviluppo integrato.</span><span class="sxs-lookup"><span data-stu-id="a9979-121">To set /libpath in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="a9979-122">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="a9979-122">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="a9979-123">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="a9979-123">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="a9979-124">2.  Fare clic sulla scheda **Riferimenti**.</span><span class="sxs-lookup"><span data-stu-id="a9979-124">2.  Click the **References** tab.</span></span><br /><span data-ttu-id="a9979-125">3.  Fare clic su di **fanno riferimento a percorsi...** pulsante.</span><span class="sxs-lookup"><span data-stu-id="a9979-125">3.  Click the **Reference Paths...** button.</span></span><br /><span data-ttu-id="a9979-126">4.  Nel **percorsi di riferimento** finestra di dialogo immettere il nome della directory nel **cartella:** casella.</span><span class="sxs-lookup"><span data-stu-id="a9979-126">4.  In the **Reference Paths** dialog box, enter the directory name in the **Folder:** box.</span></span><br /><span data-ttu-id="a9979-127">5.  Fare clic su **aggiungere la cartella**.</span><span class="sxs-lookup"><span data-stu-id="a9979-127">5.  Click **Add Folder**.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="a9979-128">Esempio</span><span class="sxs-lookup"><span data-stu-id="a9979-128">Example</span></span>  
 <span data-ttu-id="a9979-129">Il codice seguente Compila `T2.vb` per creare un file .exe.</span><span class="sxs-lookup"><span data-stu-id="a9979-129">The following code compiles `T2.vb` to create an .exe file.</span></span> <span data-ttu-id="a9979-130">Il compilatore cerca nella directory di lavoro, nella directory radice dell'unità c: e nella directory dell'unità c: nuovi assembly riferimenti ad assembly.</span><span class="sxs-lookup"><span data-stu-id="a9979-130">The compiler looks in the working directory, in the root directory of the C: drive, and in the New Assemblies directory of the C: drive for assembly references.</span></span>  
  
```console  
vbc -libpath:c:\;"c:\New Assemblies" -reference:t2.dll t2.vb  
```  
  
## <a name="see-also"></a><span data-ttu-id="a9979-131">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="a9979-131">See Also</span></span>  
 [<span data-ttu-id="a9979-132">Assembly e Global Assembly Cache</span><span class="sxs-lookup"><span data-stu-id="a9979-132">Assemblies and the Global Assembly Cache</span></span>](../../../visual-basic/programming-guide/concepts/assemblies-gac/index.md)  
 [<span data-ttu-id="a9979-133">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="a9979-133">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="a9979-134">Esempi di righe di comando di compilazione</span><span class="sxs-lookup"><span data-stu-id="a9979-134">Sample Compilation Command Lines</span></span>](../../../visual-basic/reference/command-line-compiler/sample-compilation-command-lines.md)
