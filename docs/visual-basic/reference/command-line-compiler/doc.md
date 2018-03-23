---
title: -doc
ms.date: 03/10/2018
ms.prod: .net
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
author: rpetrusha
ms.author: ronpet
ms.openlocfilehash: 0948b9ef0675541ca595bb297e01e62c9d79a181
ms.sourcegitcommit: 498799639937c89de777361aab74261efe7b79ea
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/22/2018
---
# <a name="-doc"></a><span data-ttu-id="d7b14-102">-doc</span><span class="sxs-lookup"><span data-stu-id="d7b14-102">-doc</span></span>
<span data-ttu-id="d7b14-103">Elabora commenti sulla documentazione in un file XML.</span><span class="sxs-lookup"><span data-stu-id="d7b14-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="d7b14-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="d7b14-104">Syntax</span></span>  
  
```  
-doc[+ | -]  
' -or-  
-doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="d7b14-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="d7b14-105">Arguments</span></span>  
  
|<span data-ttu-id="d7b14-106">Termine</span><span class="sxs-lookup"><span data-stu-id="d7b14-106">Term</span></span>|<span data-ttu-id="d7b14-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="d7b14-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="d7b14-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="d7b14-108">`+` &#124; `-`</span></span>|<span data-ttu-id="d7b14-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="d7b14-109">Optional.</span></span> <span data-ttu-id="d7b14-110">Specificando +, o semplicemente `-doc`, indica al compilatore di generare informazioni relative alla documentazione e inserirle in un file XML.</span><span class="sxs-lookup"><span data-stu-id="d7b14-110">Specifying +, or just `-doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="d7b14-111">Specifica di `-` è l'equivalente della specifica di non `-doc`, non causando alcuna informazione di documentazione da creare.</span><span class="sxs-lookup"><span data-stu-id="d7b14-111">Specifying `-` is the equivalent of not specifying `-doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="d7b14-112">Richiesto se è usato `-doc:`.</span><span class="sxs-lookup"><span data-stu-id="d7b14-112">Required if `-doc:` is used.</span></span> <span data-ttu-id="d7b14-113">Specifica il file XML di output, che viene popolato con i commenti dai file di codice sorgente della compilazione.</span><span class="sxs-lookup"><span data-stu-id="d7b14-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="d7b14-114">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="d7b14-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="d7b14-115">Note</span><span class="sxs-lookup"><span data-stu-id="d7b14-115">Remarks</span></span>  
 <span data-ttu-id="d7b14-116">Il `-doc` opzione controlli se il compilatore genera un file XML contenente i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="d7b14-116">The `-doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="d7b14-117">Se si utilizza il `-doc:file` sintassi, il `file` parametro specifica il nome del file XML.</span><span class="sxs-lookup"><span data-stu-id="d7b14-117">If you use the `-doc:file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="d7b14-118">Se si utilizza `-doc` o `-doc+`, il compilatore prende il nome del file XML dal file eseguibile o libreria che il compilatore sta creando.</span><span class="sxs-lookup"><span data-stu-id="d7b14-118">If you use `-doc` or `-doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="d7b14-119">Se si utilizza `-doc-` o non si specifica il `-doc` opzione, il compilatore non crea un file XML.</span><span class="sxs-lookup"><span data-stu-id="d7b14-119">If you use `-doc-` or do not specify the `-doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="d7b14-120">Nei file di codice sorgente, i commenti della documentazione possono precedere le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="d7b14-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="d7b14-121">Definite dall'utente tipi, ad esempio un [classe](../../../visual-basic/language-reference/statements/class-statement.md) o [interfaccia](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="d7b14-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="d7b14-122">I membri, ad esempio un campo, [evento](../../../visual-basic/language-reference/statements/event-statement.md), [proprietà](../../../visual-basic/language-reference/statements/property-statement.md), [funzione](../../../visual-basic/language-reference/statements/function-statement.md), o [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="d7b14-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="d7b14-123">Per utilizzare il file XML generato con il [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) funzionalità, si supponga che il nome del file del file XML sia lo stesso dell'assembly a cui si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="d7b14-123">To use the generated XML file with the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] [IntelliSense](/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="d7b14-124">Verificare che il file XML è nella stessa directory dell'assembly in modo che quando viene fatto riferimento all'assembly nel [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] progetto, il file XML sia possibile.</span><span class="sxs-lookup"><span data-stu-id="d7b14-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="d7b14-125">File di documentazione XML non sono necessari per IntelliSense funzioni per il codice all'interno di un progetto o all'interno dei progetti a cui fa riferimento un progetto.</span><span class="sxs-lookup"><span data-stu-id="d7b14-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="d7b14-126">A meno che non esegue la compilazione con `/target:module`, il file XML contiene il tag `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="d7b14-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="d7b14-127">Questi tag specificano il nome del file contenente il manifesto dell'assembly per il file di output della compilazione.</span><span class="sxs-lookup"><span data-stu-id="d7b14-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="d7b14-128">Vedere [tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) per informazioni sulla generazione di documentazione dai commenti nel codice.</span><span class="sxs-lookup"><span data-stu-id="d7b14-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="d7b14-129">Per impostare - ambiente di sviluppo integrato di documenti in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="d7b14-129">To set -doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="d7b14-130">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="d7b14-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="d7b14-131">Scegliere **Proprietà** dal menu **Progetto**.</span><span class="sxs-lookup"><span data-stu-id="d7b14-131">On the **Project** menu, click **Properties**.</span></span> <br /><span data-ttu-id="d7b14-132">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="d7b14-132">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="d7b14-133">3.  Impostare il valore di **file di documentazione XML generare** casella.</span><span class="sxs-lookup"><span data-stu-id="d7b14-133">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="d7b14-134">Esempio</span><span class="sxs-lookup"><span data-stu-id="d7b14-134">Example</span></span>  
 <span data-ttu-id="d7b14-135">Vedere [documentare il codice con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) per un esempio.</span><span class="sxs-lookup"><span data-stu-id="d7b14-135">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d7b14-136">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d7b14-136">See Also</span></span>  
 [<span data-ttu-id="d7b14-137">Compilatore della riga di comando di Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d7b14-137">Visual Basic Command-Line Compiler</span></span>](../../../visual-basic/reference/command-line-compiler/index.md)  
 [<span data-ttu-id="d7b14-138">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="d7b14-138">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
