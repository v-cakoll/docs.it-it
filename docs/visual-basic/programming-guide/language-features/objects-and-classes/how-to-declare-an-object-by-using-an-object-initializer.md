---
title: 'Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 775c40cbb62272f913297d5a58914a0c82c5a7d7
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59305312"
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Procedura: Dichiarare un oggetto usando un inizializzatore di oggetto (Visual Basic)
Gli inizializzatori di oggetto consentono di dichiarare e creare un'istanza di una classe in un'unica istruzione. Inoltre, è possibile inizializzare uno o più membri dell'istanza nello stesso momento, senza richiamare un costruttore con parametri.  
  
 Quando si usa un inizializzatore di oggetto per creare un'istanza di un tipo denominato, viene chiamato il costruttore predefinito per la classe, seguito dall'inizializzazione dei membri definiti nell'ordine specificato.  
  
 La procedura seguente illustra come creare un'istanza di un `Student` classi in tre modi diversi. La classe ha nome, cognome e proprietà della classe anno, tra gli altri. Ognuna delle tre dichiarazioni crea una nuova istanza della `Student`, con la proprietà `First` impostato su "Michael," proprietà `Last` impostato su "Tucker", e tutti gli altri membri impostano sui valori predefiniti. Il risultato di ogni dichiarazione della procedura è equivalente all'esempio seguente, che non utilizza un inizializzatore di oggetto.  
  
 [!code-vb[VbVbalrObjectInit#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#20)]  
  
 Per un'implementazione del `Student` classe, vedere [come: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). È possibile copiare il codice da quell'argomento per configurare la classe e creare un elenco di `Student` oggetti da utilizzare.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Per creare un oggetto di una classe denominata con un inizializzatore di oggetto  
  
1. Iniziare la dichiarazione come se si intendesse usare un costruttore.  
  
     `Dim student1 As New Student`  
  
2. Digitare la parola chiave `With`, seguito da un elenco di inizializzazione tra parentesi graffe.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3. Nell'elenco di inizializzazione, includere ogni proprietà che si desidera inizializzare e assegnare un valore iniziale a esso. Il nome della proprietà è preceduto da un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#21)]  
  
     È possibile inizializzare uno o più membri della classe.  
  
4. In alternativa, è possibile dichiarare una nuova istanza della classe e quindi assegnare un valore a esso. Innanzitutto, dichiarare un'istanza di `Student`:  
  
     `Dim student2 As Student`  
  
5. Avviare la creazione di un'istanza di `Student` in modo normale.  
  
     `Dim student2 As Student = New Student`  
  
6. Tipo `With` e quindi un inizializzatore di oggetto per inizializzare uno o più membri della nuova istanza.  
  
     [!code-vb[VbVbalrObjectInit#22](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#22)]  
  
7. È possibile semplificare la definizione nel passaggio precedente omettendo `As Student`. In questo caso, il compilatore determina che `student3` è un'istanza di `Student` tramite inferenza del tipo locale.  
  
     [!code-vb[VbVbalrObjectInit#23](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrObjectInit/VB/Class2.vb#23)]  
  
     Per altre informazioni, vedere [Local Type Inference](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Vedere anche

- [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Procedura: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)
- [Inizializzatori di oggetto: Tipi denominati e anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)
- [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
