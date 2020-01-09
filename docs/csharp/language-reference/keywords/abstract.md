---
title: abstract - Riferimenti per C#
ms.date: 07/20/2015
f1_keywords:
- abstract
- abstract_CSharpKeyword
helpviewer_keywords:
- abstract keyword [C#]
ms.assetid: b0797770-c1f3-4b4d-9441-b9122602a6bb
ms.openlocfilehash: 96e8bbce2e67c316d5cd1cd78e3e2506dabead25
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75713856"
---
# <a name="abstract-c-reference"></a>abstract (Riferimenti per C#)
Il modificatore `abstract` indica che l'oggetto in fase di modifica ha un'implementazione mancante o incompleta. Il modificatore abstract può essere usato con classi, metodi, proprietà, indicizzatori ed eventi. Usare il modificatore `abstract` in una dichiarazione di classe per indicare che una classe verrà usata solo come classe di base per altre classi e che non verrà creata un'istanza relativamente alla stessa. I membri contrassegnati come astratti devono essere implementati da classi non astratte che derivano dalla classe astratta.
  
## <a name="example"></a>Esempio  
 In questo esempio, la classe `Square` deve eseguire un'implementazione di `GetArea` poiché deriva da `Shape`:  
  
 [!code-csharp[csrefKeywordsModifiers#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#1)]
  
 Le classi astratte hanno le caratteristiche seguenti:  
  
- Non è possibile creare un'istanza di una classe astratta.  
  
- Una classe astratta può contenere funzioni di accesso e metodi astratti.  
  
- Non è possibile modificare una classe astratta con il modificatore [sealed](./sealed.md) perché i due modificatori hanno significati opposti. Il modificatore `sealed` impedisce a una classe che venga ereditata e il modificatore `abstract` richiede una classe da ereditare.  
  
- Una classe non astratta derivata da una classe astratta deve includere implementazioni effettive di tutte le funzioni di accesso e di tutti i metodi astratti ereditati.  
  
 Usare il modificatore `abstract` in una dichiarazione di metodo o proprietà per indicare che il metodo o proprietà non contiene implementazioni.  
  
 I metodi astratti hanno le caratteristiche seguenti:  
  
- Un metodo astratto è implicitamente un metodo virtuale.  
  
- Le dichiarazioni di metodi astratti sono consentite solo in classi astratte.  
  
- Poiché una dichiarazione di un metodo astratto non offre alcuna implementazione effettiva, non c'è nessun corpo del metodo. La dichiarazione del metodo termina semplicemente con un punto e virgola e non ci sono parentesi graffe ({ }) dopo la firma. Ad esempio:  
  
    ```csharp  
    public abstract void MyMethod();  
    ```  
  
     L'implementazione viene specificata tramite l'[override](./override.md) di un metodo, che è un membro di una classe non astratta.  
  
- Non è possibile usare il modificatore [static](./static.md) o [virtual](./virtual.md) in una dichiarazione di un metodo astratto.  
  
 Le proprietà astratte si comportano come i metodi astratti, ad eccezione delle differenze nella sintassi di dichiarazione e di chiamata.  
  
- Non è possibile usare il modificatore `abstract` su una proprietà static.  
  
- Una proprietà astratta ereditata può essere sottoposta a override in una classe derivata includendo una dichiarazione di proprietà che usa il modificatore di [override](./override.md).  
  
 Per altre informazioni sulle classi astratte, vedere [Classi e membri delle classi astratte e sealed](../../programming-guide/classes-and-structs/abstract-and-sealed-classes-and-class-members.md).  
  
 Una classe astratta deve specificare l'implementazione per tutti i membri di interfaccia.  
  
 Una classe astratta che implementa un'interfaccia può eseguire il mapping dei metodi di interfaccia su metodi astratti. Ad esempio:  
  
[!code-csharp[csrefKeywordsModifiers#2](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#2)]
  
## <a name="example"></a>Esempio  
 In questo esempio, la classe `DerivedClass` è derivata da una classe di base astratta `BaseClass`. La classe astratta contiene un metodo astratto, `AbstractMethod`, e due proprietà astratte, `X` e `Y`.  
  
[!code-csharp[csrefKeywordsModifiers#3](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csrefKeywordsModifiers/CS/csrefKeywordsModifiers.cs#3)]
  
 Nell'esempio precedente, se si prova a creare un'istanza della classe astratta tramite un'istruzione simile alla seguente:  
  
```csharp
BaseClass bc = new BaseClass();   // Error  
```  
  
si ottiene un messaggio di errore che informa che il compilatore non può creare un'istanza della classe astratta "BaseClass".  
  
## <a name="c-language-specification"></a>Specifica del linguaggio C#  
 [!INCLUDE[CSharplangspec](~/includes/csharplangspec-md.md)]  
  
## <a name="see-also"></a>Vedere anche

- [Riferimenti per C#](../index.md)
- [Guida per programmatori C#](../../programming-guide/index.md)
- [Modificatori](index.md)
- [virtual](./virtual.md)
- [override](./override.md)
- [Parole chiave di C#](./index.md)
