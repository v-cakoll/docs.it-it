---
title: 'Procedura: inizializzare oggetti utilizzando un inizializzatore di oggetto (Guida per programmatori C#)'
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-csharp
ms.topic: article
dev_langs:
- CSharp
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
caps.latest.revision: 20
author: BillWagner
ms.author: wiwagn
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
ms.translationtype: HT
ms.sourcegitcommit: 306c608dc7f97594ef6f72ae0f5aaba596c936e1
ms.openlocfilehash: 01f2391680d9236b42f0d015b944b8f12455d0c8
ms.contentlocale: it-it
ms.lasthandoff: 07/28/2017

---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Procedura: inizializzare oggetti utilizzando un inizializzatore di oggetto (Guida per programmatori C#)
È possibile usare gli inizializzatori di oggetto per inizializzare gli oggetti tipo in modo dichiarativo, senza richiamare in modo esplicito un costruttore per il tipo.  
  
 Nell'esempio seguente viene illustrato come usare gli inizializzatori di oggetto con gli oggetti denominati. Il compilatore elabora gli inizializzatori di oggetto accedendo al costruttore di istanza predefinito e quindi elaborando le inizializzazioni dei membri. Pertanto, se il costruttore predefinito viene dichiarato come `private` nella classe, gli inizializzatori di oggetto che richiedono l'accesso pubblico avranno esito negativo.  
  
 Se si definisce un tipo anonimo, è necessario usare un inizializzatore di oggetto. Per altre informazioni, vedere [Procedura: Restituire sottoinsiemi di proprietà degli elementi in una query](../../../csharp/programming-guide/classes-and-structs/how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come inizializzare un nuovo tipo `StudentName` usando inizializzatori di oggetto.  
  
 [!code-cs[csProgGuideLINQ#35](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_1.cs)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come inizializzare una raccolta di tipi `StudentName` usando un inizializzatore di insieme. Si noti che un inizializzatore di insieme è una serie di inizializzatori di oggetto con valori delimitati da virgole.  
  
 [!code-cs[csProgGuideLINQ#36](../../../csharp/programming-guide/arrays/codesnippet/CSharp/how-to-initialize-objects-by-using-an-object-initializer_2.cs)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 Per eseguire questo codice, copiare e incollare la classe in un progetto di applicazione console di Visual C# creato in [!INCLUDE[vsprvs](~/includes/vsprvs-md.md)].   
  
## <a name="see-also"></a>Vedere anche  
 [Guida per programmatori C#](../../../csharp/programming-guide/index.md)   
 [Inizializzatori di oggetto e di raccolta](../../../csharp/programming-guide/classes-and-structs/object-and-collection-initializers.md)

