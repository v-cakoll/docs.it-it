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
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Proprietà predefinita &#39; &lt;nomeproprietà1&gt; &#39; è in conflitto con proprietà predefinita &#39; &lt;propertyname2&gt; &#39; in &#39; &lt;classname&gt; &#39;e pertanto deve essere dichiarato come &#39;ombreggiature&#39;
Una proprietà è dichiarata con lo stesso nome di una proprietà definita nella classe base. In questo caso, la proprietà di questa classe deve nascondere le proprietà della classe base.  
  
 Si tratta di un messaggio di avviso. Per impostazione predefinita viene usato`Shadows` . Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40007  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Aggiungere il `Shadows` parola chiave per la dichiarazione o modificare il nome della proprietà da dichiarare.  
  
## <a name="see-also"></a>Vedere anche  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
