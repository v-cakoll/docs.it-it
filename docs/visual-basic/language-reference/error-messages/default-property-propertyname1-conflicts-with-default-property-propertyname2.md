---
title: Proprietà predefinita &#39; &lt;nomeproprietà1&gt; &#39; è in conflitto con proprietà predefinita &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;classname&gt; &#39;e pertanto deve essere dichiarato come &#39;ombreggiature&#39;
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: b305f7a59a9865ebeb6b6f53607757b719fb4d41
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33586624"
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="cfaa2-102">Proprietà predefinita &#39; &lt;nomeproprietà1&gt; &#39; è in conflitto con proprietà predefinita &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;classname&gt; &#39;e pertanto deve essere dichiarato come &#39;ombreggiature&#39;</span><span class="sxs-lookup"><span data-stu-id="cfaa2-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="cfaa2-103">Una proprietà è dichiarata con lo stesso nome di una proprietà definita nella classe base.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="cfaa2-104">In questo caso, la proprietà di questa classe deve nascondere le proprietà della classe base.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="cfaa2-105">Si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-105">This message is a warning.</span></span> <span data-ttu-id="cfaa2-106">Per impostazione predefinita viene usato`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="cfaa2-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="cfaa2-107">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="cfaa2-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="cfaa2-108">**ID errore:** BC40007</span><span class="sxs-lookup"><span data-stu-id="cfaa2-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="cfaa2-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="cfaa2-109">To correct this error</span></span>  
  
-   <span data-ttu-id="cfaa2-110">Aggiungere il `Shadows` parola chiave per la dichiarazione o modificare il nome della proprietà da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="cfaa2-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="cfaa2-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="cfaa2-111">See Also</span></span>  
 [<span data-ttu-id="cfaa2-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="cfaa2-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="cfaa2-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="cfaa2-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
