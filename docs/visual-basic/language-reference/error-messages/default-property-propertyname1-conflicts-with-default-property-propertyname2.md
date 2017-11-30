---
title: "Proprietà predefinita &#39; &lt;nomeproprietà1&gt;&#39; è in conflitto con una proprietà predefinita &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; ClassName&gt;&#39; quindi deve essere dichiarato &#39; Shadows &#39;"
ms.date: 07/20/2015
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: devlang-visual-basic
ms.topic: article
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords: BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
ms.openlocfilehash: af92c06f6d07b6ea64a05b9043547a46e3679111
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="default-property-39ltpropertyname1gt39-conflicts-with-default-property-39ltpropertyname2gt39-in-39ltclassnamegt39-and-so-should-be-declared-39shadows39"></a>Proprietà predefinita &#39; &lt;nomeproprietà1&gt;&#39; è in conflitto con una proprietà predefinita &#39;&lt; propertyName2&gt;&#39; in &#39;&lt; ClassName&gt;&#39; quindi deve essere dichiarato &#39; Shadows &#39;
Una proprietà è dichiarata con lo stesso nome di una proprietà definita nella classe base. In questo caso, la proprietà di questa classe deve nascondere le proprietà della classe base.  
  
 Si tratta di un messaggio di avviso. Per impostazione predefinita viene usato`Shadows` . Per ulteriori informazioni su come nascondere gli avvisi o considerarli come errori, vedere [configurazione degli avvisi in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40007  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Aggiungere il `Shadows` parola chiave per la dichiarazione o modificare il nome della proprietà da dichiarare.  
  
## <a name="see-also"></a>Vedere anche  
 [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)  
 [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
