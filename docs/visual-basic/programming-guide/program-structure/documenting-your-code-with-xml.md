---
title: Documentazione del codice tramite XML (Visual Basic)
ms.custom: ''
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: ''
ms.suite: ''
ms.technology:
- devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML [Visual Basic], documenting code
- XML comments, Visual Basic
- Visual Basic code, documenting with XML
ms.assetid: a0d35dc7-c5f9-4d74-92ff-a1c6f28d5235
caps.latest.revision: 17
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: d132fa514008d072158a0e6bedaff511c55b18c0
ms.sourcegitcommit: 2042de78fcdceebb6b8ac4b7a292b93e8782cbf5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/27/2018
---
# <a name="documenting-your-code-with-xml-visual-basic"></a><span data-ttu-id="7281a-102">Documentazione del codice tramite XML (Visual Basic)</span><span class="sxs-lookup"><span data-stu-id="7281a-102">Documenting Your Code with XML (Visual Basic)</span></span>
<span data-ttu-id="7281a-103">In Visual Basic, è possibile documentare il codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="7281a-103">In Visual Basic, you can document your code using XML</span></span>  
  
## <a name="xml-documentation-comments"></a><span data-ttu-id="7281a-104">Commenti relativi alla documentazione XML</span><span class="sxs-lookup"><span data-stu-id="7281a-104">XML Documentation Comments</span></span>  
 <span data-ttu-id="7281a-105">Visual Basic fornisce un modo semplice per creare automaticamente la documentazione XML per i progetti.</span><span class="sxs-lookup"><span data-stu-id="7281a-105">Visual Basic provides an easy way to automatically create XML documentation for projects.</span></span> <span data-ttu-id="7281a-106">È possibile generare automaticamente uno scheletro XML per i tipi e membri e quindi fornire i riepiloghi, documentazione descrittiva per ogni parametro e altre note.</span><span class="sxs-lookup"><span data-stu-id="7281a-106">You can automatically generate an XML skeleton for your types and members, and then provide summaries, descriptive documentation for each parameter, and other remarks.</span></span> <span data-ttu-id="7281a-107">Con il programma di installazione appropriato, la documentazione XML viene generata automaticamente in un file XML con lo stesso nome del progetto e l'estensione XML.</span><span class="sxs-lookup"><span data-stu-id="7281a-107">With the appropriate setup, the XML documentation is automatically emitted into an XML file with the same name as your project and the .xml extension.</span></span> <span data-ttu-id="7281a-108">Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="7281a-108">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
 <span data-ttu-id="7281a-109">Il file XML può essere utilizzato o manipolazione come XML.</span><span class="sxs-lookup"><span data-stu-id="7281a-109">The XML file can be consumed or otherwise manipulated as XML.</span></span> <span data-ttu-id="7281a-110">Questo file si trova nella stessa directory del file di .exe o DLL di output del progetto.</span><span class="sxs-lookup"><span data-stu-id="7281a-110">This file is located in the same directory as the output .exe or .dll file of your project.</span></span>  
  
 <span data-ttu-id="7281a-111">Documentazione XML inizia con `'''`.</span><span class="sxs-lookup"><span data-stu-id="7281a-111">XML documentation starts with `'''`.</span></span> <span data-ttu-id="7281a-112">L'elaborazione di questi commenti presenta alcune restrizioni:</span><span class="sxs-lookup"><span data-stu-id="7281a-112">The processing of these comments has some restrictions:</span></span>  
  
-   <span data-ttu-id="7281a-113">La documentazione deve essere in codice XML ben formato.</span><span class="sxs-lookup"><span data-stu-id="7281a-113">The documentation must be well-formed XML.</span></span> <span data-ttu-id="7281a-114">Se il codice XML non è corretto, viene generato un avviso e il file di documentazione contiene un commento per informare che si è verificato un errore.</span><span class="sxs-lookup"><span data-stu-id="7281a-114">If the XML is not well formed, a warning is generated and the documentation file contains a comment saying that an error was encountered.</span></span>  
  
-   <span data-ttu-id="7281a-115">Gli sviluppatori sono liberi di creare set di tag personalizzati.</span><span class="sxs-lookup"><span data-stu-id="7281a-115">Developers are free to create their own set of tags.</span></span> <span data-ttu-id="7281a-116">È un set di tag (vedere "Sezioni correlate" in questo argomento).</span><span class="sxs-lookup"><span data-stu-id="7281a-116">There is a recommended set of tags (see "Related Sections" in this topic).</span></span> <span data-ttu-id="7281a-117">Alcuni tag consigliati hanno un significato speciale:</span><span class="sxs-lookup"><span data-stu-id="7281a-117">Some of the recommended tags have special meanings:</span></span>  
  
    -   <span data-ttu-id="7281a-118">Il tag \< viene usato per descrivere i parametri.</span><span class="sxs-lookup"><span data-stu-id="7281a-118">The \<param> tag is used to describe parameters.</span></span> <span data-ttu-id="7281a-119">Se usato, il compilatore verifica che il parametro esista e che tutti i parametri siano descritti nella documentazione.</span><span class="sxs-lookup"><span data-stu-id="7281a-119">If used, the compiler will verify that the parameter exists and that all parameters are described in the documentation.</span></span> <span data-ttu-id="7281a-120">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="7281a-120">If the verification fails, the compiler issues a warning.</span></span>  
  
    -   <span data-ttu-id="7281a-121">L'attributo `cref` può essere associato a qualsiasi tag per fornire un riferimento a un elemento del codice.</span><span class="sxs-lookup"><span data-stu-id="7281a-121">The `cref` attribute can be attached to any tag to provide a reference to a code element.</span></span> <span data-ttu-id="7281a-122">Il compilatore verifica l'esistenza di questo elemento di codice.</span><span class="sxs-lookup"><span data-stu-id="7281a-122">The compiler verifies that this code element exists.</span></span> <span data-ttu-id="7281a-123">Se la verifica ha esito negativo, il compilatore genera un avviso.</span><span class="sxs-lookup"><span data-stu-id="7281a-123">If the verification fails, the compiler issues a warning.</span></span> <span data-ttu-id="7281a-124">Il compilatore rispetta inoltre eventuali `Imports` istruzioni durante la ricerca di un tipo di `cref` attributo.</span><span class="sxs-lookup"><span data-stu-id="7281a-124">The compiler also respects any `Imports` statements when looking for a type described in the `cref` attribute.</span></span>  
  
    -   <span data-ttu-id="7281a-125">Il \<riepilogo > tag è utilizzato da IntelliSense in Visual Studio per visualizzare informazioni aggiuntive sul tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="7281a-125">The \<summary> tag is used by IntelliSense in Visual Studio to display additional information about a type or member.</span></span>  
  
## <a name="related-sections"></a><span data-ttu-id="7281a-126">Sezioni correlate</span><span class="sxs-lookup"><span data-stu-id="7281a-126">Related Sections</span></span>  
 <span data-ttu-id="7281a-127">Per informazioni dettagliate sulla creazione di un file XML con i commenti della documentazione, vedere gli argomenti seguenti:</span><span class="sxs-lookup"><span data-stu-id="7281a-127">For details on creating an XML file with documentation comments, see the following topics:</span></span>  
  
-   [<span data-ttu-id="7281a-128">/doc</span><span class="sxs-lookup"><span data-stu-id="7281a-128">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)  
  
-   [<span data-ttu-id="7281a-129">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="7281a-129">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
  
-   [<span data-ttu-id="7281a-130">Elaborazione del file XML</span><span class="sxs-lookup"><span data-stu-id="7281a-130">Processing the XML File</span></span>](../../../visual-basic/programming-guide/program-structure/processing-the-xml-file.md)  
  
-   [<span data-ttu-id="7281a-131">Procedura: Creare documentazione XML</span><span class="sxs-lookup"><span data-stu-id="7281a-131">How to: Create XML Documentation</span></span>](../../../visual-basic/programming-guide/program-structure/how-to-create-xml-documentation.md)  
  
-   [<span data-ttu-id="7281a-132">Strumenti XML in Visual Studio</span><span class="sxs-lookup"><span data-stu-id="7281a-132">XML Tools in Visual Studio</span></span>](/visualstudio/xml-tools/xml-tools-in-visual-studio)  
  
## <a name="see-also"></a><span data-ttu-id="7281a-133">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="7281a-133">See Also</span></span>  
 [<span data-ttu-id="7281a-134">Sviluppo di applicazioni con Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7281a-134">Developing Applications with Visual Basic</span></span>](../../../visual-basic/developing-apps/index.md)  
 [<span data-ttu-id="7281a-135">Guida per programmatori Visual Basic</span><span class="sxs-lookup"><span data-stu-id="7281a-135">Visual Basic Programming Guide</span></span>](../../../visual-basic/programming-guide/index.md)
