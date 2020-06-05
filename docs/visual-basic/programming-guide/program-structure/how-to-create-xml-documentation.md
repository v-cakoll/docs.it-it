---
title: 'Procedura: creare documentazione XML'
ms.date: 07/20/2015
helpviewer_keywords:
- XML comments
- XML documentation [Visual Basic], creating
ms.assetid: 27b5b06c-09b9-496a-8245-f9542d846230
ms.openlocfilehash: 1421cc85beba42b3cf3656c34b1d02347fbaf164
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84403239"
---
# <a name="how-to-create-xml-documentation-in-visual-basic"></a><span data-ttu-id="40897-102">Procedura: creare documentazione XLM in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="40897-102">How to: Create XML Documentation in Visual Basic</span></span>

<span data-ttu-id="40897-103">Questo esempio illustra come aggiungere commenti alla documentazione XML al codice.</span><span class="sxs-lookup"><span data-stu-id="40897-103">This example shows how to add XML documentation comments to your code.</span></span>

[!INCLUDE[note_settings_general](~/includes/note-settings-general-md.md)]

## <a name="to-create-xml-documentation-for-a-type-or-member"></a><span data-ttu-id="40897-104">Per creare la documentazione XML per un tipo o un membro</span><span class="sxs-lookup"><span data-stu-id="40897-104">To create XML documentation for a type or member</span></span>

1. <span data-ttu-id="40897-105">Nell' **editor di codice**posizionare il cursore sulla riga al di sopra del tipo o del membro per il quale si desidera creare la documentazione.</span><span class="sxs-lookup"><span data-stu-id="40897-105">In the **Code Editor**, position your cursor on the line above the type or member for which you want to create documentation.</span></span>

2. <span data-ttu-id="40897-106">Digitare `'''` (tre virgolette singole).</span><span class="sxs-lookup"><span data-stu-id="40897-106">Type `'''` (three single-quotation marks).</span></span>

    <span data-ttu-id="40897-107">Un'ossatura XML per il tipo o il membro viene aggiunta nell' **editor di codice**.</span><span class="sxs-lookup"><span data-stu-id="40897-107">An XML skeleton for the type or member is added in the **Code Editor**.</span></span>

3. <span data-ttu-id="40897-108">Aggiungere informazioni descrittive tra i tag appropriati.</span><span class="sxs-lookup"><span data-stu-id="40897-108">Add descriptive information between the appropriate tags.</span></span>

    > [!NOTE]
    > <span data-ttu-id="40897-109">Se si aggiungono righe aggiuntive all'interno del blocco di documentazione XML, ogni riga deve iniziare con `'''` .</span><span class="sxs-lookup"><span data-stu-id="40897-109">If you add additional lines within the XML documentation block, each line must begin with `'''`.</span></span>

4. <span data-ttu-id="40897-110">Aggiungere codice aggiuntivo che utilizza il tipo o il membro con i nuovi commenti della documentazione XML.</span><span class="sxs-lookup"><span data-stu-id="40897-110">Add additional code that uses the type or member with the new XML documentation comments.</span></span>

    <span data-ttu-id="40897-111">IntelliSense consente di visualizzare il testo del \<summary> tag per il tipo o il membro.</span><span class="sxs-lookup"><span data-stu-id="40897-111">IntelliSense displays the text from the \<summary> tag for the type or member.</span></span>

5. <span data-ttu-id="40897-112">Compilare il codice per generare un file XML contenente i commenti della documentazione.</span><span class="sxs-lookup"><span data-stu-id="40897-112">Compile the code to generate an XML file containing the documentation comments.</span></span> <span data-ttu-id="40897-113">Per ulteriori informazioni, vedere [-doc](../../reference/command-line-compiler/doc.md).</span><span class="sxs-lookup"><span data-stu-id="40897-113">For more information, see [-doc](../../reference/command-line-compiler/doc.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="40897-114">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="40897-114">See also</span></span>

- [<span data-ttu-id="40897-115">Documentazione del codice tramite XML</span><span class="sxs-lookup"><span data-stu-id="40897-115">Documenting Your Code with XML</span></span>](documenting-your-code-with-xml.md)
- [<span data-ttu-id="40897-116">Tag di commento XML</span><span class="sxs-lookup"><span data-stu-id="40897-116">XML Comment Tags</span></span>](../../language-reference/xmldoc/index.md)
- [<span data-ttu-id="40897-117">-doc</span><span class="sxs-lookup"><span data-stu-id="40897-117">-doc</span></span>](../../reference/command-line-compiler/doc.md)
