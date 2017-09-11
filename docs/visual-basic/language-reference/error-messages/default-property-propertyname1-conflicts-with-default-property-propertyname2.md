---
title: "Proprietà predefinita &quot;&lt;propertyname1&gt;&quot;è in conflitto con la proprietà predefinita&quot;&lt;propertyname2&gt;&quot;in&quot;&lt;classname&gt;&quot; e quindi deve essere dichiarata &quot;Shadows&quot; | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
dev_langs:
- VB
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 9
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
ms.openlocfilehash: 6eac9e0fdc468e27afac82a8a7c9b2251a8f7317
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="c94d8-102">Proprietà predefinita '&lt;propertyname1&gt;'è in conflitto con la proprietà predefinita'&lt;propertyname2&gt;'in'&lt;classname&gt;' e quindi deve essere dichiarata 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="c94d8-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="c94d8-103">Viene dichiarata una proprietà con lo stesso nome di una proprietà definita nella classe di base.</span><span class="sxs-lookup"><span data-stu-id="c94d8-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="c94d8-104">In questo caso, la proprietà di questa classe deve nascondere la proprietà della classe base.</span><span class="sxs-lookup"><span data-stu-id="c94d8-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="c94d8-105">Si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="c94d8-105">This message is a warning.</span></span> <span data-ttu-id="c94d8-106">`Shadows`Per impostazione predefinita, viene utilizzato.</span><span class="sxs-lookup"><span data-stu-id="c94d8-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="c94d8-107">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="c94d8-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](https://docs.microsoft.com/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="c94d8-108">**ID errore:** BC40007</span><span class="sxs-lookup"><span data-stu-id="c94d8-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="c94d8-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="c94d8-109">To correct this error</span></span>  
  
-   <span data-ttu-id="c94d8-110">Aggiungere il `Shadows` parola chiave per la dichiarazione o la modifica viene dichiarato il nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="c94d8-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="c94d8-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="c94d8-111">See Also</span></span>  
 <span data-ttu-id="c94d8-112">[Ombreggiature](../../../visual-basic/language-reference/modifiers/shadows.md) </span><span class="sxs-lookup"><span data-stu-id="c94d8-112">[Shadows](../../../visual-basic/language-reference/modifiers/shadows.md) </span></span>  
<span data-ttu-id="c94d8-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span><span class="sxs-lookup"><span data-stu-id="c94d8-113"> [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)</span></span>
