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
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>La proprietà predefinita '\<propertyname1>' è in conflitto con la proprietà predefinita '\<propertyname2> nella base '\<classname>', quindi deve essere dichiarata 'Shadows'
Una proprietà viene dichiarata con lo stesso nome di una proprietà definita nella classe base. In questa situazione, la proprietà in questa classe deve nascondere la proprietà della classe base.  
  
 Si tratta di un messaggio di avviso. Per impostazione predefinita viene usato`Shadows` . Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40007  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
- Aggiungere la `Shadows` parola chiave alla dichiarazione o modificare il nome della proprietà dichiarata.  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](../modifiers/shadows.md)
- [Shadowing in Visual Basic](../../programming-guide/language-features/declared-elements/shadowing.md)
