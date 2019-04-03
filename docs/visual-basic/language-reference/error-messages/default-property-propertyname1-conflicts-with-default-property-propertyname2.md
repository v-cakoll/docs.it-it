---
title: La proprietà predefinita '<propertyname1>' è in conflitto con la proprietà predefinita '<propertyname2> nella base '<classname>', quindi deve essere dichiarata 'Shadows'
ms.date: 07/20/2015
f1_keywords:
- vbc40007
- bc40007
helpviewer_keywords:
- BC40007
ms.assetid: 692ccf76-5715-4f11-a972-84cf9de30bc1
ms.openlocfilehash: ab45278b2e1199282e3066c34828b9bda716e162
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58813171"
---
# <a name="default-property-propertyname1-conflicts-with-default-property-propertyname2-in-classname-and-so-should-be-declared-shadows"></a>Proprietà predefinita '\<nomeproprietà1 >' è in conflitto con la proprietà predefinita '\<nomeproprietà2 >' in '\<NomeClasse >' e pertanto deve essere dichiarato come 'Shadows'
Una proprietà viene dichiarata con lo stesso nome di una proprietà definita nella classe di base. In questo caso, la proprietà di questa classe deve nascondere le proprietà della classe base.  
  
 Si tratta di un messaggio di avviso. Per impostazione predefinita viene usato`Shadows` . Per altre informazioni su come nascondere gli avvisi o considerarli come errori, vedere [Configuring Warnings in Visual Basic](/visualstudio/ide/configuring-warnings-in-visual-basic).  
  
 **ID errore:** BC40007  
  
## <a name="to-correct-this-error"></a>Per correggere l'errore  
  
-   Aggiungere il `Shadows` una parola chiave per la dichiarazione o modificare il nome della proprietà da dichiarare.  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shadowing in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/shadowing.md)
