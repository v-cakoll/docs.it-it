---
title: 'Procedura: creare documentazione XLM in Visual Basic'
ms.custom: 
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: "17"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: 63b6485de5aba2ca49d54a057045bec2062d12dd
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="d142b-102">Procedura: creare documentazione XLM in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="d142b-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="d142b-103">In questo esempio viene illustrato come aggiungere commenti della documentazione XML al codice.</span><span class="sxs-lookup"><span data-stu-id="d142b-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="d142b-104">Per creare la documentazione XML per un tipo o membro</span><span class="sxs-lookup"><span data-stu-id="d142b-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="d142b-105">Nel **Editor di codice**, posizionare il cursore sulla riga di sopra del tipo o membro per il quale si desidera creare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="d142b-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="d142b-106">Tipo `'''` (tre virgolette singole).</span><span class="sxs-lookup"><span data-stu-id="d142b-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="d142b-107">Uno scheletro XML per il tipo o il membro viene aggiunto nel **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="d142b-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="d142b-108">Aggiungere informazioni descrittive tra i tag appropriati.</span><span class="sxs-lookup"><span data-stu-id="d142b-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="d142b-109">Se si aggiungono le righe all'interno del blocco di documentazione XML, ogni riga deve iniziare con `'''`.</span><span class="sxs-lookup"><span data-stu-id="d142b-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="d142b-110">Aggiungere codice che utilizza il tipo o il membro con i nuovi commenti della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="d142b-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="d142b-111">IntelliSense consente di visualizzare il testo di \<riepilogo > tag per il tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="d142b-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="d142b-112">Compilare il codice per generare un file XML contenente i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="d142b-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="d142b-113">Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="d142b-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="d142b-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="d142b-114">See Also</span></span>  
 [<span data-ttu-id="d142b-115">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="d142b-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)  
 [<span data-ttu-id="d142b-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="d142b-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md)  
 [<span data-ttu-id="d142b-117">/doc</span><span class="sxs-lookup"><span data-stu-id="d142b-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
