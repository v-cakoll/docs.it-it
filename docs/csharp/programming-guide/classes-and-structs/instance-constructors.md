---
title: Costruttori di istanze - Guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- constructors [C#], instance constructors
- instance constructors [C#]
ms.assetid: 24663779-c1e5-4af4-a942-ca554e4c542d
ms.openlocfilehash: 621b8ca7510b0b9916c9c46f201ff77402c3c655
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/14/2020
ms.locfileid: "75964716"
---
# <a name="instance-constructors-c-programming-guide"></a>Costruttori di istanze (Guida per programmatori C#)

I costruttori di istanze vengono usati per creare e inizializzare qualsiasi variabile membro di istanza quando si usa l'espressione [new](../../language-reference/operators/new-operator.md) per creare un oggetto di una [classe](../../language-reference/keywords/class.md). Per inizializzare una classe [statica](../../language-reference/keywords/static.md) o variabili statiche in una classe non statica, definire un costruttore statico. Per altre informazioni, vedere [Costruttori statici](./static-constructors.md).  
  
 Nell'esempio seguente viene illustrato un costruttore di istanze:  
  
 [!code-csharp[csProgGuideObjects#5](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#5)]  
  
> [!NOTE]
> Per maggior chiarezza, questa classe contiene campi pubblici. L'uso di campi pubblici non è una procedura di programmazione consigliata, perché consente a qualsiasi metodo in qualsiasi punto di un programma di accedere senza restrizioni e senza verifiche ai componenti interni di un oggetto. I membri dati in genere devono essere privati e l'accesso ad essi deve essere consentito solo tramite metodi e proprietà della classe.  
  
 Questo costruttore di istanze viene chiamato ogni volta che viene creato un oggetto basato sulla classe `Coords`. Un costruttore come questo, che non accetta argomenti, viene chiamato *costruttore senza parametri *. È spesso utile, tuttavia, per fornire costruttori aggiuntivi. È ad esempio possibile aggiungere un costruttore alla classe `Coords` che consente di specificare i valori iniziali dei membri dati:  
  
 [!code-csharp[csProgGuideObjects#76](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#76)]  
  
 Ciò consente di creare oggetti `Coords` con valori iniziali predefiniti o specifici, come illustrato di seguito:  
  
 [!code-csharp[csProgGuideObjects#77](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#77)]  
  
 Se una classe non ha un costruttore, viene generato automaticamente un costruttore senza parametri e per inizializzare i campi dell'oggetto vengono usati valori predefiniti. Ad esempio, un valore [int](../../language-reference/builtin-types/integral-numeric-types.md) viene inizializzato su 0. Per informazioni sui valori predefiniti del tipo, vedere [Valori predefiniti dei tipi C .](../../language-reference/builtin-types/default-values.md) Poiché il costruttore senza parametri della classe `Coords` inizializza tutti i membri dati su zero, può pertanto essere rimosso completamente senza che ciò modifichi il funzionamento della classe. Per un esempio completo sull'uso di più costruttori, vedere l'esempio 1 più avanti in questo argomento. Per un esempio di costruttore generato automaticamente, vedere l'esempio 2.  
  
 I costruttori di istanze possono anche essere usati per chiamare i costruttori di istanze delle classi di base. Il costruttore di classi può chiamare il costruttore della classe di base mediante l'inizializzatore, ad esempio:  
  
 [!code-csharp[csProgGuideObjects#78](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#78)]  
  
 In questo esempio la classe `Circle` passa i valori che rappresentano il raggio e l'altezza al costruttore fornito da `Shape` da cui deriva `Circle`. Per un esempio completo sull'uso di `Shape` e `Circle` vedere l'esempio 3 di questo argomento.  
  
## <a name="example-1"></a>Esempio 1  
 L'esempio riportato di seguito illustra una classe con due costruttori di classi, uno senza argomenti e uno con due argomenti.  
  
 [!code-csharp[csProgGuideObjects#4](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#4)]  
  
## <a name="example-2"></a>Esempio 2  
 In questo esempio, la classe `Person` non ha alcun costruttore. In questo caso viene fornito automaticamente un costruttore senza parametri e i campi vengono inizializzati sui rispettivi valori predefiniti.  
  
 [!code-csharp[csProgGuideObjects#8](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#8)]  
  
 Si noti che il valore predefinito di `age` è `0` e il valore predefinito di `name` è `null`.
  
## <a name="example-3"></a>Esempio 3  
 Nell'esempio riportato di seguito viene illustrato l'uso dell'inizializzatore della classe di base. La classe `Circle` è derivata dalla classe generale `Shape`e la classe `Cylinder` è derivata dalla classe `Circle`. Il costruttore di ogni classe derivata usa il relativo inizializzatore della classe di base.  
  
 [!code-csharp[csProgGuideObjects#9](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#9)]  
  
 Per altri esempi su come chiamare i costruttori della classe di base, vedere [virtual](../../language-reference/keywords/virtual.md), [override](../../language-reference/keywords/override.md) e [base](../../language-reference/keywords/base.md).  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Classi e struct](./index.md)
- [Costruttori](./constructors.md)
- [Finalizzatori](./destructors.md)
- [Statico](../../language-reference/keywords/static.md)
