---
title: /doc | Documenti di Microsoft
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
dev_langs:
- VB
helpviewer_keywords:
- doc compiler option [Visual Basic]
- -doc compiler option [Visual Basic]
- /doc compiler option [Visual Basic]
ms.assetid: 5fc32ec9-a149-4648-994c-a8d0cccd0a65
caps.latest.revision: 18
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 974c41ba6ba4104a7fe17146390e14ccfbb7a521
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="doc"></a><span data-ttu-id="26277-102">/doc</span><span class="sxs-lookup"><span data-stu-id="26277-102">/doc</span></span>
<span data-ttu-id="26277-103">Elabora commenti sulla documentazione in un file XML.</span><span class="sxs-lookup"><span data-stu-id="26277-103">Processes documentation comments to an XML file.</span></span>  
  
## <a name="syntax"></a><span data-ttu-id="26277-104">Sintassi</span><span class="sxs-lookup"><span data-stu-id="26277-104">Syntax</span></span>  
  
```  
/doc[+ | -]  
' -or-  
/doc:file  
```  
  
## <a name="arguments"></a><span data-ttu-id="26277-105">Argomenti</span><span class="sxs-lookup"><span data-stu-id="26277-105">Arguments</span></span>  
  
|<span data-ttu-id="26277-106">Termine</span><span class="sxs-lookup"><span data-stu-id="26277-106">Term</span></span>|<span data-ttu-id="26277-107">Definizione</span><span class="sxs-lookup"><span data-stu-id="26277-107">Definition</span></span>|  
|---|---|  
|<span data-ttu-id="26277-108">`+` &#124; `-`</span><span class="sxs-lookup"><span data-stu-id="26277-108">`+` &#124; `-`</span></span>|<span data-ttu-id="26277-109">Facoltativo.</span><span class="sxs-lookup"><span data-stu-id="26277-109">Optional.</span></span> <span data-ttu-id="26277-110">Specificando +, o semplicemente `/doc`, indica al compilatore di generare informazioni relative alla documentazione e inserirle in un file XML.</span><span class="sxs-lookup"><span data-stu-id="26277-110">Specifying +, or just `/doc`, causes the compiler to generate documentation information and place it in an XML file.</span></span> <span data-ttu-id="26277-111">Specifica di `-` è l'equivalente della specifica di non `/doc`, non causando alcuna informazione di documentazione da creare.</span><span class="sxs-lookup"><span data-stu-id="26277-111">Specifying `-` is the equivalent of not specifying `/doc`, causing no documentation information to be created.</span></span>|  
|`file`|<span data-ttu-id="26277-112">Richiesto se è usato `/doc:`.</span><span class="sxs-lookup"><span data-stu-id="26277-112">Required if `/doc:` is used.</span></span> <span data-ttu-id="26277-113">Specifica il file XML di output, che viene popolato con i commenti dai file di codice sorgente della compilazione.</span><span class="sxs-lookup"><span data-stu-id="26277-113">Specifies the output XML file, which is populated with the comments from the source-code files of the compilation.</span></span> <span data-ttu-id="26277-114">Se il nome del file contiene uno spazio, racchiudere il nome tra virgolette ("").</span><span class="sxs-lookup"><span data-stu-id="26277-114">If the file name contains a space, surround the name with quotation marks (" ").</span></span>|  
  
## <a name="remarks"></a><span data-ttu-id="26277-115">Note</span><span class="sxs-lookup"><span data-stu-id="26277-115">Remarks</span></span>  
 <span data-ttu-id="26277-116">Il `/doc` opzione consente di controllare se il compilatore genera un file XML contenente i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="26277-116">The `/doc` option controls whether the compiler generates an XML file containing the documentation comments.</span></span> <span data-ttu-id="26277-117">Se si utilizza il `/doc:``file` sintassi, il `file` parametro specifica il nome del file XML.</span><span class="sxs-lookup"><span data-stu-id="26277-117">If you use the `/doc:``file` syntax, the `file` parameter specifies the name of the XML file.</span></span> <span data-ttu-id="26277-118">Se si utilizza `/doc` o `/doc+`, il compilatore utilizza il nome del file XML del file eseguibile o della libreria che il compilatore sta creando.</span><span class="sxs-lookup"><span data-stu-id="26277-118">If you use `/doc` or `/doc+`, the compiler takes the XML file name from the executable file or library that the compiler is creating.</span></span> <span data-ttu-id="26277-119">Se si utilizza `/doc-` o non si specifica il `/doc` opzione, il compilatore non crea un file XML.</span><span class="sxs-lookup"><span data-stu-id="26277-119">If you use `/doc-` or do not specify the `/doc` option, the compiler does not create an XML file.</span></span>  
  
 <span data-ttu-id="26277-120">Nei file di codice sorgente, i commenti della documentazione possono precedere le definizioni seguenti:</span><span class="sxs-lookup"><span data-stu-id="26277-120">In source-code files, documentation comments can precede the following definitions:</span></span>  
  
-   <span data-ttu-id="26277-121">Definite dall'utente tipi, ad esempio un [classe](../../../visual-basic/language-reference/statements/class-statement.md) o [interfaccia](../../../visual-basic/language-reference/statements/interface-statement.md)</span><span class="sxs-lookup"><span data-stu-id="26277-121">User-defined types, such as a [class](../../../visual-basic/language-reference/statements/class-statement.md) or [interface](../../../visual-basic/language-reference/statements/interface-statement.md)</span></span>  
  
-   <span data-ttu-id="26277-122">I membri, ad esempio un campo, [evento](../../../visual-basic/language-reference/statements/event-statement.md), [proprietà](../../../visual-basic/language-reference/statements/property-statement.md), [funzione](../../../visual-basic/language-reference/statements/function-statement.md), o [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span><span class="sxs-lookup"><span data-stu-id="26277-122">Members, such as a field, [event](../../../visual-basic/language-reference/statements/event-statement.md), [property](../../../visual-basic/language-reference/statements/property-statement.md), [function](../../../visual-basic/language-reference/statements/function-statement.md), or [subroutine](../../../visual-basic/language-reference/statements/sub-statement.md).</span></span>  
  
 <span data-ttu-id="26277-123">Utilizzare il file XML generato con il [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) funzionalità, si supponga che il nome del file del file XML sia lo stesso dell'assembly a cui si desidera supportare.</span><span class="sxs-lookup"><span data-stu-id="26277-123">To use the generated XML file with the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] [IntelliSense](https://docs.microsoft.com/visualstudio/ide/using-intellisense) feature, let the file name of the XML file be the same as the assembly you want to support.</span></span> <span data-ttu-id="26277-124">Assicurarsi che il file XML sia nella stessa directory dell'assembly in modo che quando viene fatto riferimento all'assembly nel [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] progetto, il file XML è disponibile anche.</span><span class="sxs-lookup"><span data-stu-id="26277-124">Make sure the XML file is in the same directory as the assembly so that when the assembly is referenced in the [!INCLUDE[vsprvs](../../../csharp/includes/vsprvs_md.md)] project, the .xml file is found as well.</span></span> <span data-ttu-id="26277-125">File di documentazione XML non sono necessari per IntelliSense funzioni per il codice all'interno di un progetto o all'interno dei progetti a cui fa riferimento un progetto.</span><span class="sxs-lookup"><span data-stu-id="26277-125">XML documentation files are not required for IntelliSense to work for code within a project or within projects referenced by a project.</span></span>  
  
 <span data-ttu-id="26277-126">A meno che non esegue la compilazione con `/target:module`, il file XML contiene i tag `<assembly></assembly>`.</span><span class="sxs-lookup"><span data-stu-id="26277-126">Unless you compile with `/target:module`, the XML file contains the tags `<assembly></assembly>`.</span></span> <span data-ttu-id="26277-127">Questi tag specificano il nome del file contenente il manifesto dell'assembly per il file di output della compilazione.</span><span class="sxs-lookup"><span data-stu-id="26277-127">These tags specify the name of the file containing the assembly manifest for the output file of the compilation.</span></span>  
  
 <span data-ttu-id="26277-128">Vedere [tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) per informazioni sulla generazione di documentazione dai commenti nel codice.</span><span class="sxs-lookup"><span data-stu-id="26277-128">See [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) for ways to generate documentation from comments in your code.</span></span>  
  
|<span data-ttu-id="26277-129">Per impostare l'opzione /doc in Visual Studio ambiente di sviluppo integrato</span><span class="sxs-lookup"><span data-stu-id="26277-129">To set /doc in the Visual Studio integrated development environment</span></span>|  
|---|  
|<span data-ttu-id="26277-130">1.  Selezionare un progetto in **Esplora soluzioni**.</span><span class="sxs-lookup"><span data-stu-id="26277-130">1.  Have a project selected in **Solution Explorer**.</span></span> <span data-ttu-id="26277-131">Nel **progetto** menu, fare clic su **proprietà**.</span><span class="sxs-lookup"><span data-stu-id="26277-131">On the **Project** menu, click **Properties**.</span></span> <span data-ttu-id="26277-132">Per altre informazioni, vedere [Introduzione a Creazione progetti](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span><span class="sxs-lookup"><span data-stu-id="26277-132">For more information, see [Introduction to the Project Designer](http://msdn.microsoft.com/en-us/898dd854-c98d-430c-ba1b-a913ce3c73d7).</span></span><br /><span data-ttu-id="26277-133">2.  Fare clic sulla scheda **Compila**.</span><span class="sxs-lookup"><span data-stu-id="26277-133">2.  Click the **Compile** tab.</span></span><br /><span data-ttu-id="26277-134">3.  Impostare il valore di **file di documentazione XML genera** casella.</span><span class="sxs-lookup"><span data-stu-id="26277-134">3.  Set the value in the **Generate XML documentation file** box.</span></span>|  
  
## <a name="example"></a><span data-ttu-id="26277-135">Esempio</span><span class="sxs-lookup"><span data-stu-id="26277-135">Example</span></span>  
 <span data-ttu-id="26277-136">Vedere [documentare il codice con XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) per un esempio.</span><span class="sxs-lookup"><span data-stu-id="26277-136">See [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) for a sample.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="26277-137">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="26277-137">See Also</span></span>  
 <span data-ttu-id="26277-138">[Compilatore della riga di comando di Visual Basic](../../../visual-basic/reference/command-line-compiler/index.md) </span><span class="sxs-lookup"><span data-stu-id="26277-138">[Visual Basic Command-Line Compiler](../../../visual-basic/reference/command-line-compiler/index.md) </span></span>  
<span data-ttu-id="26277-139"> [Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)</span><span class="sxs-lookup"><span data-stu-id="26277-139"> [Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)</span></span>
