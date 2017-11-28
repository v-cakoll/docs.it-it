---
title: Classi e membri delle classi astratte e sealed (Guida per programmatori C#)
ms.date: 07/20/2015
ms.prod: .net
ms.technology: devlang-csharp
ms.topic: article
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
caps.latest.revision: "14"
author: BillWagner
ms.author: wiwagn
ms.openlocfilehash: dac7570c018bd577faac4540e4d800cc11143578
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a>Classi e membri delle classi astratte e sealed (Guida per programmatori C#)
La parola chiave [abstract](../../../csharp/language-reference/keywords/abstract.md) consente di creare classi e membri di [classe](../../../csharp/language-reference/keywords/class.md), che sono incompleti e devono essere implementati in una classe derivata.  
  
 La parola chiave [sealed](../../../csharp/language-reference/keywords/sealed.md) consente di impedire l'ereditarietà di una classe o di determinati membri di classe contrassegnati in precedenza come [virtuali](../../../csharp/language-reference/keywords/virtual.md).  
  
## <a name="abstract-classes-and-class-members"></a>Classi e membri di classi astratte  
 Una classe può essere dichiarata astratta inserendo la parola chiave `abstract` prima della definizione della classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#13](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_1.cs)]  
  
 Non è possibile creare un'istanza di una classe astratta. Lo scopo di una classe astratta è quello di fornire una definizione comune di una classe base condivisibile da più classi derivate. Una libreria di classi può, ad esempio, definire una classe astratta utilizzata come parametro per molte funzioni e richiedere ai programmatori che utilizzano tale libreria di fornire un'implementazione personalizzata della classe creando una classe derivata.  
  
 Le classi astratte possono inoltre definire metodi astratti aggiungendo la parola chiave `abstract` prima del tipo restituito del metodo. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#14](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_2.cs)]  
  
 I metodi astratti non prevedono implementazione, pertanto la definizione del metodo è seguita da un punto e virgola, anziché da un normale blocco di metodi. Le classi derivate della classe astratta devono implementare tutti i metodi astratti. Quando una classe astratta eredita un metodo virtuale da una classe base, la classe astratta può eseguire l'override del metodo virtuale con un metodo astratto. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#15](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_3.cs)]  
  
 Un metodo `virtual` dichiarato `abstract` rimane virtuale in qualsiasi classe che eredita dalla classe astratta. Una classe che eredita un metodo astratto non può accedere all'implementazione originale del metodo. Nell'esempio precedente, `DoWork` sulla classe F non può chiamare `DoWork` sulla classe D. In questo modo una classe astratta può imporre alle classi derivate di fornire nuove implementazioni per i metodi virtuali.  
  
## <a name="sealed-classes-and-class-members"></a>Classi e membri di classi sealed  
 Le classi possono essere dichiarate [sealed](../../../csharp/language-reference/keywords/sealed.md) inserendo la parola chiave `sealed` prima della definizione della classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#16](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_4.cs)]  
  
 Una classe sealed non può essere utilizzata come classe base. Per questo motivo non può neppure essere una classe astratta. Le classi sealed impediscono la derivazione. Poiché non possono mai essere utilizzate come classe base, in alcune ottimizzazioni runtime la chiamata ai membri di classi sealed può risultare leggermente più rapida.  
  
 Un metodo, un indicizzatore, una proprietà o un evento di una classe derivata che esegue l'override di un membro virtuale della classe base può dichiarare tale membro come sealed. In questo modo viene negato l'aspetto virtuale del membro per qualsiasi ulteriore classe derivata. A questo scopo è necessario inserire la parola chiave `sealed` prima della parola chiave [override](../../../csharp/language-reference/keywords/override.md) nella dichiarazione del membro di classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#17](../../../csharp/programming-guide/classes-and-structs/codesnippet/CSharp/abstract-and-sealed-classes-and-class-members_5.cs)]  
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)  
 [Classi e struct](../../../csharp/programming-guide/classes-and-structs/index.md)  
 [Ereditarietà](../../../csharp/programming-guide/classes-and-structs/inheritance.md)  
 [Metodi](../../../csharp/programming-guide/classes-and-structs/methods.md)  
 [Campi](../../../csharp/programming-guide/classes-and-structs/fields.md)  
 [Procedura: Definire proprietà astratte](../../../csharp/programming-guide/classes-and-structs/how-to-define-abstract-properties.md)
