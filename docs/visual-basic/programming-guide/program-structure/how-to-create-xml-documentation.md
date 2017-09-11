---
title: 'Procedura: creare documentazione XLM in Visual Basic | Documenti di Microsoft'
ms.custom: 
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
- XML comments
- XML documentation, creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
caps.latest.revision: 17
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
ms.sourcegitcommit: 31905a37f09db5f5192123f0118252fbe8b02eff
ms.openlocfilehash: 3171877f4fa1913b5535d71d671cea97b5a22850
ms.contentlocale: it-it
ms.lasthandoff: 05/26/2017

---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="45c26-102">Procedura: creare documentazione XLM in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="45c26-102">How to: Create XML Documentation in Visual Basic</span></span>
<span data-ttu-id="45c26-103">In questo esempio viene illustrato come aggiungere commenti di documentazione XML per il codice.</span><span class="sxs-lookup"><span data-stu-id="45c26-103">This example shows how to add XML documentation comments to your code.</span></span>  
  
[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]  
  
### <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="45c26-104">Creazione di documentazione XML per un tipo o membro</span><span class="sxs-lookup"><span data-stu-id="45c26-104">To create XML documentation for a type or member</span></span>  
  
1.  <span data-ttu-id="45c26-105">Nel **Editor di codice**, posizionare il cursore sulla riga sopra il tipo o il membro per il quale si desidera creare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="45c26-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>  
  
2.  <span data-ttu-id="45c26-106">Tipo `'''` (tre virgolette singole).</span><span class="sxs-lookup"><span data-stu-id="45c26-106">Type `'''` (three single-quotation marks).</span></span>  
  
     <span data-ttu-id="45c26-107">Viene aggiunto uno scheletro XML per il tipo o membro di **Editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="45c26-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>  
  
3.  <span data-ttu-id="45c26-108">Aggiungere informazioni descrittive tra i tag appropriati.</span><span class="sxs-lookup"><span data-stu-id="45c26-108">Add descriptive information between the appropriate tags.</span></span>  
  
    > [!NOTE]
    >  <span data-ttu-id="45c26-109">Se si aggiungono le righe all'interno del blocco di documentazione XML, ogni riga deve iniziare con `'''`.</span><span class="sxs-lookup"><span data-stu-id="45c26-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>  
  
4.  <span data-ttu-id="45c26-110">Aggiungere codice che utilizza il tipo o il membro con i nuovi commenti della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="45c26-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>  
  
     <span data-ttu-id="45c26-111">IntelliSense consente di visualizzare il testo di \<riepilogo > tag per il tipo o membro.</span><span class="sxs-lookup"><span data-stu-id="45c26-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>  
  
5.  <span data-ttu-id="45c26-112">Compilare il codice per generare un file XML contenente i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="45c26-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="45c26-113">Per ulteriori informazioni, vedere [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="45c26-113">For more information, see [/doc](../../../visual-basic/reference/command-line-compiler/doc.md).</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="45c26-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="45c26-114">See Also</span></span>  
 <span data-ttu-id="45c26-115">[Documentazione del codice tramite XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span><span class="sxs-lookup"><span data-stu-id="45c26-115">[Documenting Your Code with XML](../../../visual-basic/programming-guide/program-structure/documenting-your-code-with-xml.md) </span></span>  
<span data-ttu-id="45c26-116"> [Tag di commento XML](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span><span class="sxs-lookup"><span data-stu-id="45c26-116"> [XML Comment Tags](../../../visual-basic/language-reference/xmldoc/recommended-xml-tags-for-documentation-comments.md) </span></span>  
<span data-ttu-id="45c26-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span><span class="sxs-lookup"><span data-stu-id="45c26-117"> [/doc](../../../visual-basic/reference/command-line-compiler/doc.md)</span></span>
