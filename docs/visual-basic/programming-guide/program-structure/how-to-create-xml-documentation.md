---
title: 'Procedura: Creare documentazione XML in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: d67724aad6cd3e7af30531328d85e89937390dd1
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54551371"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="1c8f4-102">Procedura: Creare documentazione XML in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="1c8f4-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="1c8f4-103">In questo esempio viene illustrato come aggiungere commenti in formato documentazione XML nel codice.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="1c8f4-104">Per creare documentazione XML per un tipo o membro</span><span class="sxs-lookup"><span data-stu-id="1c8f4-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="1c8f4-105">Nel **Editor di codice**, posizionare il cursore sulla riga sopra il tipo o membro per cui si desidera creare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="1c8f4-106">Tipo `'''` (tre virgolette singole).</span><span class="sxs-lookup"><span data-stu-id="1c8f4-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="1c8f4-107">Viene aggiunto uno scheletro XML per il tipo o membro di **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="1c8f4-108">Aggiungere informazioni descrittive tra i tag appropriati.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="1c8f4-109">Se si aggiungono altre righe all'interno del blocco di documentazione XML, ogni riga deve iniziare con `'''`.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="1c8f4-110">Aggiungere altro codice che usa il tipo o membro con i nuovi commenti della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="1c8f4-111">IntelliSense visualizza il testo dal \<riepilogo > tag per il tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="1c8f4-112">Compilare il codice per generare un file XML contenente i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="1c8f4-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="1c8f4-113">Per altre informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="1c8f4-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="1c8f4-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="1c8f4-114">See also</span></span>
- [<span data-ttu-id="1c8f4-115">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="1c8f4-115">Documenting Your Code with XML</span></span>](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md)
- [<span data-ttu-id="1c8f4-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="1c8f4-116">XML Comment Tags</span></span>](../../../visual-basic/language-reference/xmldoc/index.md)
- [<span data-ttu-id="1c8f4-117">/doc</span><span class="sxs-lookup"><span data-stu-id="1c8f4-117">/doc</span></span>](../../../visual-basic/reference/command-line-compiler/doc.md)
