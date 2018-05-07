---
title: 'Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto (Visual Basic)'
ms.date: 07/20/2015
helpviewer_keywords:
- declaring objects using object initializer
- object initializers [Visual Basic]
- initializers [Visual Basic]
- Video How tos, Visual Basic
ms.assetid: 0f53a553-efd6-466d-80bf-6b679e5cd174
ms.openlocfilehash: 3a372ba91377b53c87c05976e416ca8ed55ccbbe
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-an-object-by-using-an-object-initializer-visual-basic"></a>Procedura: dichiarare un oggetto utilizzando un inizializzatore di oggetto (Visual Basic)
Gli inizializzatori di oggetto consentono di dichiarare e creare un'istanza di una classe in un'unica istruzione. Inoltre, è possibile inizializzare uno o più membri dell'istanza nello stesso momento, senza richiamare un costruttore con parametri.  
  
 Quando si utilizza un inizializzatore di oggetto per creare un'istanza di un tipo denominato, viene chiamato il costruttore predefinito per la classe, seguito dall'inizializzazione dei membri designati nell'ordine specificato.  
  
 La procedura seguente viene illustrato come creare un'istanza di un `Student` classe in tre modi diversi. La classe dispone di nome, cognome e proprietà della classe anno, tra gli altri. Ognuna delle tre dichiarazioni crea una nuova istanza della `Student`, con proprietà `First` impostata su "Michael," proprietà `Last` impostata su "Figli" e impostano tutti gli altri membri in base ai valori predefiniti. Il risultato di ogni dichiarazione nella procedura è equivalente all'esempio seguente, che non utilizza un inizializzatore di oggetto.  
  
 [!code-vb[VbVbalrObjectInit#20](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_1.vb)]  
  
 Per un'implementazione del `Student` classe, vedere [procedura: creare un elenco di elementi di](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md). È possibile copiare il codice da tale argomento per configurare la classe e creare un elenco di `Student` oggetti da utilizzare.  
  
### <a name="to-create-an-object-of-a-named-class-by-using-an-object-initializer"></a>Per creare un oggetto di una classe denominata con un inizializzatore di oggetto  
  
1.  Iniziare la dichiarazione come se si sceglie di utilizzare un costruttore.  
  
     `Dim student1 As New Student`  
  
2.  Digitare la parola chiave `With`, seguito da un elenco di inizializzazione tra parentesi graffe.  
  
     `Dim student1 As New Student With { <initialization list> }`  
  
3.  Nell'elenco di inizializzazione, includere ogni proprietà che si desidera inizializzare e assegnarvi un valore iniziale. Il nome della proprietà è preceduto da un punto.  
  
     [!code-vb[VbVbalrObjectInit#21](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_2.vb)]  
  
     È possibile inizializzare uno o più membri della classe.  
  
4.  In alternativa, è possibile dichiarare una nuova istanza della classe e quindi assegnare un valore. Innanzitutto, dichiarare un'istanza di `Student`:  
  
     `Dim student2 As Student`  
  
5.  Avviare la creazione di un'istanza di `Student` nel modo normale.  
  
     `Dim student2 As Student = New Student`  
  
6.  Tipo `With` e quindi un inizializzatore di oggetto per inizializzare i membri di uno o più di una nuova istanza.  
  
     [!code-vb[VbVbalrObjectInit#22](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_3.vb)]  
  
7.  È possibile semplificare la definizione nel passaggio precedente omettendo `As Student`. In questo caso, il compilatore determina che `student3` è un'istanza di `Student` tramite l'inferenza del tipo locale.  
  
     [!code-vb[VbVbalrObjectInit#23](../../../../visual-basic/programming-guide/language-features/objects-and-classes/codesnippet/VisualBasic/how-to-declare-an-object-by-using-an-object-initializer_4.vb)]  
  
     Per ulteriori informazioni, vedere [locale l'inferenza del tipo](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Inferenza del tipo di variabile locale](../../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)  
 [Procedura: Creare un elenco di elementi](../../../../visual-basic/programming-guide/concepts/linq/how-to-create-a-list-of-items.md)  
 [Inizializzatori di oggetto: tipi denominati e tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/object-initializers-named-and-anonymous-types.md)  
 [Tipi anonimi](../../../../visual-basic/programming-guide/language-features/objects-and-classes/anonymous-types.md)
