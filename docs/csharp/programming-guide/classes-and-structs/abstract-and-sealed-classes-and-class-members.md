---
title: Classi e membri delle classi astratte e sealed - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- abstract classes [C#]
- sealed classes [C#]
- C# language, abstract classes
- C# language, sealed
ms.assetid: 99aa52f7-b435-43f9-936e-2470af734c4e
ms.openlocfilehash: 07738031f1dec05424f7c3756f49a8f1f9a2c44b
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714999"
---
# <a name="abstract-and-sealed-classes-and-class-members-c-programming-guide"></a>Classi e membri delle classi astratte e sealed (Guida per programmatori C#)
La parola chiave [abstract](../../language-reference/keywords/abstract.md) consente di creare classi e membri di [classe](../../language-reference/keywords/class.md), che sono incompleti e devono essere implementati in una classe derivata.  
  
 La parola chiave [sealed](../../language-reference/keywords/sealed.md) consente di impedire l'ereditarietà di una classe o di determinati membri di classe contrassegnati in precedenza come [virtuali](../../language-reference/keywords/virtual.md).  
  
## <a name="abstract-classes-and-class-members"></a>Classi e membri di classi astratte  
 Una classe può essere dichiarata astratta inserendo la parola chiave `abstract` prima della definizione della classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#13](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#13)]  
  
 Non è possibile creare un'istanza di una classe astratta. Lo scopo di una classe astratta è quello di fornire una definizione comune di una classe base condivisibile da più classi derivate. Una libreria di classi può, ad esempio, definire una classe astratta utilizzata come parametro per molte funzioni e richiedere ai programmatori che utilizzano tale libreria di fornire un'implementazione personalizzata della classe creando una classe derivata.  
  
 Le classi astratte possono inoltre definire metodi astratti aggiungendo la parola chiave `abstract` prima del tipo restituito del metodo. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#14](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#14)]  
  
 I metodi astratti non prevedono implementazione, pertanto la definizione del metodo è seguita da un punto e virgola, anziché da un normale blocco di metodi. Le classi derivate della classe astratta devono implementare tutti i metodi astratti. Quando una classe astratta eredita un metodo virtuale da una classe base, la classe astratta può eseguire l'override del metodo virtuale con un metodo astratto. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#15](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#15)]  
  
 Un metodo `virtual` dichiarato `abstract` rimane virtuale in qualsiasi classe che eredita dalla classe astratta. Una classe che eredita un metodo astratto non può accedere all'implementazione originale del metodo. Nell'esempio precedente, `DoWork` sulla classe F non può chiamare `DoWork` sulla classe D. In questo modo una classe astratta può imporre alle classi derivate di fornire nuove implementazioni per i metodi virtuali.  
  
## <a name="sealed-classes-and-class-members"></a>Classi e membri di classi sealed  
 Le classi possono essere dichiarate [sealed](../../language-reference/keywords/sealed.md) inserendo la parola chiave `sealed` prima della definizione della classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#16](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#16)]  
  
 Una classe sealed non può essere utilizzata come classe base. Per questo motivo non può neppure essere una classe astratta. Le classi sealed impediscono la derivazione. Poiché non possono mai essere utilizzate come classe base, in alcune ottimizzazioni runtime la chiamata ai membri di classi sealed può risultare leggermente più rapida.  
  
 Un metodo, un indicizzatore, una proprietà o un evento di una classe derivata che esegue l'override di un membro virtuale della classe base può dichiarare tale membro come sealed. In questo modo viene negato l'aspetto virtuale del membro per qualsiasi ulteriore classe derivata. A questo scopo è necessario inserire la parola chiave `sealed` prima della parola chiave [override](../../language-reference/keywords/override.md) nella dichiarazione del membro di classe. Ad esempio:  
  
 [!code-csharp[csProgGuideInheritance#17](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideInheritance/CS/Inheritance.cs#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Ereditarietà](./inheritance.md)
- [Metodi](./methods.md)
- [Campi](./fields.md)
- [Come definire le proprietà astratte](./how-to-define-abstract-properties.md)
