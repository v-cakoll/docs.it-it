---
title: 'Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: cf4954059a4b0bf015bed82a74357ecfd5f5987e
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404875"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto (Visual Basic)
Gli inizializzatori di oggetto consentono di dichiarare e creare un'istanza di una classe in un'unica istruzione. Inoltre, è possibile inizializzare uno o più membri dell'istanza contemporaneamente, senza richiamare un costruttore con parametri.  
  
 Quando si utilizza un inizializzatore di oggetto per creare un'istanza di un tipo denominato, viene chiamato il costruttore senza parametri per la classe, seguito dall'inizializzazione dei membri designati nell'ordine specificato.  
  
 Nella procedura seguente viene illustrato come creare un'istanza di una `Student` classe in tre modi diversi. La classe include le proprietà First Name, Last Name e Class year, tra le altre. Ognuna delle tre dichiarazioni crea una nuova istanza di `Student` , con la proprietà `First` impostata su "Michael", la proprietà `Last` impostata su "Tucker" e tutti gli altri membri impostati sui rispettivi valori predefiniti. Il risultato di ogni dichiarazione nella procedura è equivalente all'esempio seguente, che non usa un inizializzatore di oggetto.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Per un'implementazione della `Student` classe, vedere [procedura: creare un elenco di elementi](../../concepts/linq/how-to-create-a-list-of-items.md). È possibile copiare il codice da questo argomento per configurare la classe e creare un elenco di `Student` oggetti da usare.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Per creare un oggetto di una classe denominata utilizzando un inizializzatore di oggetto  
  
1. Iniziare la dichiarazione come se si pianificasse l'uso di un costruttore.  
  
     `Dim student1 As New Student`  
  
2. Digitare la parola chiave `With` , seguita da un elenco di inizializzazione tra parentesi graffe.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. Nell'elenco di inizializzazione includere ogni proprietà che si desidera inizializzare e assegnarvi un valore iniziale. Il nome della proprietà è preceduto da un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     È possibile inizializzare uno o più membri della classe.  
  
4. In alternativa, è possibile dichiarare una nuova istanza della classe e quindi assegnarvi un valore. Dichiarare innanzitutto un'istanza di `Student` :  
  
     `Dim student2 As Student`  
  
5. Iniziare la creazione di un'istanza di `Student` in modo normale.  
  
     `Dim student2 As Student = New Student`  
  
6. Digitare `With` e quindi un inizializzatore di oggetto per inizializzare uno o più membri della nuova istanza.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. Per semplificare la definizione nel passaggio precedente, è possibile omettere `As Student` . In tal caso, il compilatore determina che `student3` è un'istanza di utilizzando l' `Student` inferenza del tipo locale.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Per altre informazioni, vedere [inferenza dei tipi locali](../variables/local-type-inference.md).  
  
## <a name="see-also"></a>Vedere anche

- [Inferenza del tipo di variabile locale](../variables/local-type-inference.md)
- [Procedura: Creare un elenco di elementi](../../concepts/linq/how-to-create-a-list-of-items.md)
- [Inizializzatori di oggetto: tipi denominati e tipi anonimi](object-initializers-named-and-anonymous-types.md)
- [Tipi anonimi](anonymous-types.md)
