---
title: Come dichiarare e usare le proprietà di lettura/ C# scrittura-Guida alla programmazione
ms.date: 07/20/2015
helpviewer_keywords:
- get accessor [C#], declaring properties
- set accessor [C#]
- properties [C#], declaring
- read/write properties [C#]
- accessors [C#], declaring properties with
ms.assetid: a4962fef-af7e-4c4b-a929-4ae4d646ab8a
ms.openlocfilehash: 5b880cfc3ace197a3bad2f707cf55543dbe7b78e
ms.sourcegitcommit: 5f236cd78cf09593c8945a7d753e0850e96a0b80
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/07/2020
ms.locfileid: "75714924"
---
# <a name="how-to-declare-and-use-read-write-properties-c-programming-guide"></a>Come dichiarare e usare le proprietà di lettura/C# scrittura (Guida per programmatori)
Le proprietà offrono i vantaggi dei membri dati pubblici senza i rischi associati all'accesso non protetto, non controllato e non verificato ai dati di un oggetto. Ciò si ottiene tramite le *funzioni di accesso*, ovvero metodi speciali che assegnano e recuperano valori dal membro dati sottostante. La funzione di accesso [set](../../language-reference/keywords/set.md) consente l'assegnazione di valori ai membri dati, mentre la funzione di accesso [get](../../language-reference/keywords/get.md) recupera i valori dei membri dati.  
  
 Questo esempio mostra una classe `Person` con due proprietà: `Name` (string) e `Age` (int). Entrambe le proprietà forniscono le funzioni di accesso `get` e `set`, quindi vengono considerate proprietà di lettura/scrittura.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideObjects#33](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#33)]  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Nell'esempio precedente le proprietà `Name` e `Age` sono di tipo [public](../../language-reference/keywords/public.md) e includono entrambe le funzioni di accesso `get` e `set`. Ciò consente a qualsiasi oggetto di leggere e scrivere tali proprietà. A volte è tuttavia preferibile escludere una delle funzioni di accesso. Se si omette la funzione di accesso `set`, ad esempio, la proprietà diventa di sola lettura:  
  
 [!code-csharp[csProgGuideObjects#87](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#87)]  
  
 In alternativa è possibile esporre pubblicamente una funzione di accesso ma rendere l'altra privata o protetta. Per altre informazioni, vedere [Accessibilità asimmetrica delle funzioni di accesso](./restricting-accessor-accessibility.md).  
  
 Una volta dichiarate le proprietà, è possibile usarle come se si trattasse di campi della classe. Ciò consente di usare una sintassi molto semplice quando si vuole ottenere o impostare il valore di una proprietà, come nelle istruzioni seguenti:  
  
 [!code-csharp[csProgGuideObjects#35](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#35)]  
  
 Si noti che in un metodo `set` di una proprietà è disponibile una variabile `value` speciale. Questa variabile contiene il valore specificato dall'utente, ad esempio:  
  
 [!code-csharp[csProgGuideObjects#36](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#36)]  
  
 Si noti la semplice sintassi per incrementare la proprietà `Age` di un oggetto `Person`:  
  
 [!code-csharp[csProgGuideObjects#37](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#37)]  
  
 Se per modellare le proprietà venissero usati metodi `set` e `get` distinti, il codice equivalente sarebbe simile al seguente:  
  
```csharp  
person.SetAge(person.GetAge() + 1);   
```  
  
 In questo esempio viene eseguito l'override del metodo `ToString`:  
  
 [!code-csharp[csProgGuideObjects#38](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideObjects/CS/Objects.cs#38)]  
  
 Si noti che il metodo `ToString` non viene usato in modo esplicito nel programma. Viene richiamato per impostazione predefinita dalle chiamate a `WriteLine`.  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Proprietà](./properties.md)
- [Classi e struct](./index.md)
