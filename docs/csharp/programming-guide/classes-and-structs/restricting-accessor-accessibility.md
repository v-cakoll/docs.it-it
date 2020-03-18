---
title: Limitazione dell'accessibilità delle funzioni di accesso - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- read-only properties [C#]
- read-only indexers [C#]
- accessors [C#]
- properties [C#], read-only
- asymmetric accessor accessibility [C#]
- indexers [C#], read-only
ms.assetid: 6e655798-e112-4301-a680-6310a6e012e1
ms.openlocfilehash: a332fef814f0c81914eb7b8c308de68f719fbaac
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75714686"
---
# <a name="restricting-accessor-accessibility-c-programming-guide"></a>Limitazione dell'accessibilità delle funzioni di accesso (Guida per programmatori C#)
Le parti [get](../../language-reference/keywords/get.md) e [set](../../language-reference/keywords/set.md) di una proprietà o un indicizzatore sono denominate *funzioni di accesso*. Per impostazione predefinita, queste funzioni di accesso hanno la stessa visibilità o livello di accesso della proprietà o dell'indicizzatore a cui appartengono. Per altre informazioni, vedere [Livelli di accessibilità](../../language-reference/keywords/accessibility-levels.md). Tuttavia, talvolta è utile limitare l'accesso a una di queste funzioni di accesso. In genere, ciò comporta la limitazione dell'accessibilità della funzione di accesso `set`, mantenendo la funzione di accesso `get` accessibile pubblicamente. Ad esempio:  
  
 [!code-csharp[csProgGuideIndexers#6](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#6)]  
  
 In questo esempio, una proprietà denominata `Name` definisce una funzione di accesso `get` e `set`. La funzione di accesso `get` riceve il livello di accessibilità della proprietà stessa, in questo caso `public`, mentre la funzione di accesso `set` è limitata in modo esplicito applicando il modificatore di accesso [protected](../../language-reference/keywords/protected.md) alla funzione di accesso stessa.  
  
## <a name="restrictions-on-access-modifiers-on-accessors"></a>Restrizioni dei modificatori di accesso per le funzioni di accesso  
 L'uso dei modificatori delle funzioni di accesso nelle proprietà o negli indicizzatori è soggetto a queste condizioni:  
  
- È possibile usare i modificatori delle funzioni di accesso su un'interfaccia o su un'implementazione esplicita di un membro [interface](../../language-reference/keywords/interface.md).  
  
- È possibile usare i modificatori delle funzioni di accesso solo se la proprietà o l'indicizzatore ha entrambe le funzioni di accesso `set` e `get`. In questo caso, il modificatore è consentito solo per una delle due funzioni di accesso.  
  
- Se la proprietà o l'indicizzatore ha un modificatore [override](../../language-reference/keywords/override.md), il modificatore della funzione di accesso deve corrispondere alla funzione di accesso della funzione di accesso sottoposta a override, se presente.  
  
- Il livello di accessibilità nella funzione di accesso deve essere più restrittivo del livello di accessibilità nella proprietà o nell'indicizzatore stesso.  
  
## <a name="access-modifiers-on-overriding-accessors"></a>Modificatori di accesso per l'override di funzioni di accesso  
 Quando si esegue l'override di una proprietà o un indicizzatore, le funzioni di accesso sottoposte a override devono essere accessibili al codice di override. Inoltre, l'accessibilità della proprietà/indicizzatore e delle relative funzioni di accesso deve corrispondere alla proprietà/indicizzatore e alle funzioni di accesso sottoposti a override corrispondenti. Ad esempio:  
  
 [!code-csharp[csProgGuideIndexers#7](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#7)]  
  
## <a name="implementing-interfaces"></a>Implementazione di interfacce  
 Quando si usa una funzione di accesso per implementare un'interfaccia, la funzione di accesso potrebbe non disporre di un modificatore di accesso. Se tuttavia si implementa l'interfaccia usando una sola funzione di accesso, ad esempio `get`, l'altra funzione di accesso può avere un modificatore di accesso, come nell'esempio seguente:  
  
 [!code-csharp[csProgGuideIndexers#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#8)]  
  
## <a name="accessor-accessibility-domain"></a>Dominio di accessibilità della funzione di accesso  
 Se si usa un modificatore di accesso nella funzione di accesso, il [dominio di accessibilità](../../language-reference/keywords/accessibility-domain.md) della funzione di accesso è determinato da questo modificatore.  
  
 Se non è stato usato un modificatore di accesso nella funzione di accesso, il dominio di accessibilità della funzione di accesso è determinato dal livello di accessibilità della proprietà o dell'indicizzatore.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente contiene tre classi, `BaseClass`, `DerivedClass` e `MainClass`. Sono disponibili due proprietà per `BaseClass`, `Name` e `Id` in entrambe le classi. L'esempio illustra come la proprietà `Id` in `DerivedClass` può essere nascosta dalla proprietà `Id` in `BaseClass` quando si usa un modificatore di accesso restrittivo, ad esempio [protected](../../language-reference/keywords/protected.md) o [private](../../language-reference/keywords/private.md). Pertanto, quando si assegnano valori a questa proprietà, viene invece chiamata la proprietà nella classe `BaseClass`. La sostituzione del modificatore di accesso con [public](../../language-reference/keywords/public.md) renderà la proprietà accessibile.  
  
 L'esempio illustra anche che un modificatore di accesso restrittivo, quale `private` o `protected`, nella funzione di accesso `set` della proprietà `Name` in `DerivedClass` impedisce l'accesso alla funzione di accesso e genera un errore quando si esegue l'assegnazione.  
  
 [!code-csharp[csProgGuideIndexers#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideIndexers/CS/Indexers.cs#5)]  
  
## <a name="comments"></a>Commenti  
 Si noti che sostituendo la dichiarazione `new private string Id` con `new public string Id`, si otterrà l'output:  
  
 `Name and ID in the base class: Name-BaseClass, ID-BaseClass`  
  
 `Name and ID in the derived class: John, John123`  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Proprietà](./properties.md)
- [Indicizzatori](../indexers/index.md)
- [Modificatori di accesso](./access-modifiers.md)
