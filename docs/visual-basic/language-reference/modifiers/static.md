---
title: Static
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: f020756466888f51298abb423997906ddc7caff7
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350753"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Specifica che una o più variabili locali dichiarate devono continuare a esistere e mantenere i valori più recenti dopo la terminazione della routine in cui sono dichiarate.  
  
## <a name="remarks"></a>Note  
 In genere, una variabile locale di una routine cessa di esistere non appena la procedura viene arrestata. Una variabile statica continua a esistere e mantiene il valore più recente. Alla successiva chiamata della stored procedure da parte del codice, la variabile non viene reinizializzata e continua a contenere l'ultimo valore assegnato. Una variabile statica continua a esistere per la durata della classe o del modulo in cui è definita.  
  
## <a name="rules"></a>Regole  
  
- **Contesto di dichiarazione.** È possibile utilizzare `Static` solo su variabili locali. Ciò significa che il contesto di dichiarazione per una variabile di `Static` deve essere una routine o un blocco in una routine e non può essere un file di origine, uno spazio dei nomi, una classe, una struttura o un modulo.  
  
     Non è possibile utilizzare `Static` all'interno di una routine della struttura.  
  
- Non è possibile dedurre i tipi di dati di `Static` variabili locali. Per altre informazioni, vedere [inferenza dei tipi locali](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md).  
  
- **Modificatori combinati.** Non è possibile specificare `Static` insieme `ReadOnly`, `Shadows`o `Shared` nella stessa dichiarazione.  
  
## <a name="behavior"></a>Comportamento  
 Quando si dichiara una variabile statica in una procedura di `Shared`, è disponibile solo una copia della variabile statica per l'intera applicazione. È possibile chiamare una procedura `Shared` usando il nome della classe, non una variabile che punta a un'istanza della classe.  
  
 Quando si dichiara una variabile statica in una routine che non è `Shared`, è disponibile solo una copia della variabile per ogni istanza della classe. Una routine non condivisa viene chiamata utilizzando una variabile che punta a un'istanza specifica della classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'uso di `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 La variabile `Static` `totalSales` viene inizializzata su 0 solo una volta. Ogni volta che si immette `updateSales`, `totalSales` dispone ancora del valore più recente calcolato.  
  
 Il modificatore `Static` può essere usato in questo contesto:  
  
 [Istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](../../../visual-basic/language-reference/modifiers/shadows.md)
- [Shared](../../../visual-basic/language-reference/modifiers/shared.md)
- [Durata in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/lifetime.md)
- [Dichiarazione di variabile](../../../visual-basic/programming-guide/language-features/variables/variable-declaration.md)
- [Strutture](../../../visual-basic/programming-guide/language-features/data-types/structures.md)
- [Inferenza del tipo di variabile locale](../../../visual-basic/programming-guide/language-features/variables/local-type-inference.md)
- [Oggetti e classi](../../../visual-basic/programming-guide/language-features/objects-and-classes/index.md)
