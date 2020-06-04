---
title: La proprietà predefinita '<propertyname1>' è in conflitto con la proprietà predefinita '<propertyname2> nella base '<classname>', quindi deve essere dichiarata 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: 37f98ce8120d5861552819690f9d5f22c9959a0e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84409725"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a><span data-ttu-id="e4fa9-102">La proprietà predefinita '\<propertyname1>' è in conflitto con la proprietà predefinita '\<propertyname2> nella base '\<classname>', quindi deve essere dichiarata 'Shadows'</span><span class="sxs-lookup"><span data-stu-id="e4fa9-102">Default property '\<propertyname1>' conflicts with default property '\<propertyname2>' in '\<classname>' and so should be declared 'Shadows'</span></span>
<span data-ttu-id="e4fa9-103">Una proprietà viene dichiarata con lo stesso nome di una proprietà definita nella classe base.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-103">A property is declared with the same name as a property defined in the base class.</span></span> <span data-ttu-id="e4fa9-104">In questa situazione, la proprietà in questa classe deve nascondere la proprietà della classe base.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-104">In this situation, the property in this class should shadow the base class property.</span></span>  
  
 <span data-ttu-id="e4fa9-105">Si tratta di un messaggio di avviso.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-105">This message is a warning.</span></span> <span data-ttu-id="e4fa9-106">Per impostazione predefinita viene usato`Shadows` .</span><span class="sxs-lookup"><span data-stu-id="e4fa9-106">`Shadows` is assumed by default.</span></span> <span data-ttu-id="e4fa9-107">Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span><span class="sxs-lookup"><span data-stu-id="e4fa9-107">For more information about hiding warnings or treating warnings as errors, see [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).</span></span>  
  
 <span data-ttu-id="e4fa9-108">**ID errore:** BC40007</span><span class="sxs-lookup"><span data-stu-id="e4fa9-108">**Error ID:** BC40007</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e4fa9-109">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e4fa9-109">To correct this error</span></span>  
  
- <span data-ttu-id="e4fa9-110">Aggiungere la `Shadows` parola chiave alla dichiarazione o modificare il nome della proprietà dichiarata.</span><span class="sxs-lookup"><span data-stu-id="e4fa9-110">Add the `Shadows` keyword to the declaration, or change the name of the property being declared.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e4fa9-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e4fa9-111">See also</span></span>

- [<span data-ttu-id="e4fa9-112">Shadows</span><span class="sxs-lookup"><span data-stu-id="e4fa9-112">Shadows</span></span>](../modifiers/shadows.md)
- [<span data-ttu-id="e4fa9-113">Shadowing in Visual Basic</span><span class="sxs-lookup"><span data-stu-id="e4fa9-113">Shadowing in Visual Basic</span></span>](../../programming-guide/language-features/declared-elements/shadowing.md)
