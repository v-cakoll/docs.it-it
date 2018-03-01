---
title: "Proprietà predefinita &#39; &lt;nomeproprietà1&gt;&#39; è in conflitto con una proprietà predefinita &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; ClassName&gt;&#39; quindi deve essere dichiarato &#39; Shadows &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: 
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a><span data-ttu-id="6d257-102">Proprietà predefinita &#39; &lt;nomeproprietà1&gt;&#39; è in conflitto con una proprietà predefinita &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; ClassName&gt;&#39; quindi deve essere dichiarato &#39; Shadows &#39;</span><span class="sxs-lookup"><span data-stu-id="6d257-102">Default property &#39;&lt;propertyname1&gt;&#39; conflicts with default property &#39;&lt;propertyname2&gt;&#39; in &#39;&lt;classname&gt;&#39; and so should be declared &#39;Shadows&#39;</span></span>
<span data-ttu-id="6d257-103">Una proprietà è dichiarata con lo stesso nome di una proprietà definita nella classe base.</span><span class="sxs-lookup"><span data-stu-id="6d257-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="6d257-104">In questo caso, la proprietà di questa classe deve nascondere le proprietà della classe base.</span><span class="sxs-lookup"><span data-stu-id="6d257-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="6d257-105">Si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="6d257-105">This message is a warning.</span></span> <span data-ttu-id="6d257-106">Per impostazione predefinita viene usato`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="6d257-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="6d257-107">Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="6d257-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="6d257-108">**ID errore:** BC40007</span><span class="sxs-lookup"><span data-stu-id="6d257-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="6d257-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="6d257-109">To correct this error</span></span>  
  
-   <span data-ttu-id="6d257-110">Aggiungere il `Shadows` parola chiave per la dichiarazione o modificare il nome della proprietà da dichiarare.</span><span class="sxs-lookup"><span data-stu-id="6d257-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="6d257-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="6d257-111">See Also</span></span>  
 [<span data-ttu-id="6d257-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="6d257-112">Shadows</span></span>](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [<span data-ttu-id="6d257-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="6d257-113">Shadowing in Visual Basic</span></span>](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
