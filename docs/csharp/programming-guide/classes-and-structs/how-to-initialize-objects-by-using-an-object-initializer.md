---
title: Come inizializzare gli oggetti usando un inizializzatore di oggetto-guida per programmatori C#
description: Informazioni su come usare gli inizializzatori di oggetto per inizializzare gli oggetti di tipo in C# senza richiamare un costruttore. Usare un inizializzatore di oggetto per definire un tipo anonimo.
ms.date: 12/20/2018
helpviewer_keywords:
- object initializers [C#], how to use
- objects [C#], initializing
ms.assetid: 4b75ebb2-2e29-43de-929c-d736a8f27ce6
ms.openlocfilehash: 0781b168b0ae8b8383affe19d2721da67f662045
ms.sourcegitcommit: 3d84eac0818099c9949035feb96bbe0346358504
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/21/2020
ms.locfileid: "86865034"
---
# <a name="how-to-initialize-objects-by-using-an-object-initializer-c-programming-guide"></a>Come inizializzare gli oggetti usando un inizializzatore di oggetto (Guida per programmatori C#)

È possibile usare gli inizializzatori di oggetto per inizializzare gli oggetti tipo in modo dichiarativo, senza richiamare in modo esplicito un costruttore per il tipo.  
  
Nell'esempio seguente viene illustrato come usare gli inizializzatori di oggetto con gli oggetti denominati. Il compilatore elabora gli inizializzatori di oggetto accedendo al costruttore di istanza predefinito e quindi elaborando le inizializzazioni dei membri. Pertanto, se il costruttore senza parametri viene dichiarato come `private` nella classe, gli inizializzatori di oggetto che richiedono l'accesso pubblico avranno esito negativo.
  
Se si definisce un tipo anonimo, è necessario usare un inizializzatore di oggetto. Per ulteriori informazioni, vedere [come restituire subset di proprietà degli elementi in una query](how-to-return-subsets-of-element-properties-in-a-query.md).  
  
## <a name="example"></a>Esempio  

Nell'esempio seguente viene illustrato come inizializzare un nuovo tipo `StudentName` usando inizializzatori di oggetto. Questo esempio imposta le proprietà nel tipo `StudentName`:
  
[!code-csharp[InitializerObjectExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToObjectInitializers.cs#HowToObjectInitializers)]  

Gli inizializzatori di oggetto possono essere usati per impostare gli indicizzatori in un oggetto. L'esempio seguente definisce una classe `BaseballTeam` che usa un indicizzatore per ottenere e impostare i lettori in posizioni diverse. L'inizializzatore può assegnare lettori, in base all'abbreviazione per la posizione o al numero usato per gli scorecard di baseball di ogni posizione:

[!code-csharp[InitializerIndexerExample](../../../../samples/snippets/csharp/programming-guide/classes-and-structs/object-collection-initializers/HowToIndexInitializer.cs#HowToIndexInitializer)]  

## <a name="see-also"></a>Vedi anche

- [Guida per programmatori C#](../index.md)
- [Inizializzatori di oggetto e di raccolta](object-and-collection-initializers.md)
