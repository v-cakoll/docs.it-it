---
title: Statico
ms.date: 07/20/2015
f1_keywords:
- vb.Static
helpviewer_keywords:
- static modifier
- Static keyword [Visual Basic]
ms.assetid: 19013910-4658-47b6-a22e-1744b527979e
ms.openlocfilehash: 3b323d5fb1c4f1357b9f476213793c69d29b7208
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84402694"
---
# <a name="static-visual-basic"></a>Static (Visual Basic)
Specifica che una o più variabili locali dichiarate devono continuare a esistere e mantenere i valori più recenti dopo la terminazione della routine in cui sono dichiarate.  
  
## <a name="remarks"></a>Commenti  
 In genere, una variabile locale di una routine cessa di esistere non appena la procedura viene arrestata. Una variabile statica continua a esistere e mantiene il valore più recente. Alla successiva chiamata della stored procedure da parte del codice, la variabile non viene reinizializzata e continua a contenere l'ultimo valore assegnato. Una variabile statica continua a esistere per la durata della classe o del modulo in cui è definita.  
  
## <a name="rules"></a>Regole  
  
- **Contesto della dichiarazione. ** È possibile utilizzare `Static` solo su variabili locali. Ciò significa che il contesto di dichiarazione per una `Static` variabile deve essere una routine o un blocco in una routine e non può essere un file di origine, uno spazio dei nomi, una classe, una struttura o un modulo.  
  
     Non è possibile utilizzare `Static` all'interno di una routine della struttura.  
  
- `Static`Non è possibile dedurre i tipi di dati delle variabili locali. Per altre informazioni, vedere [inferenza dei tipi locali](../../programming-guide/language-features/variables/local-type-inference.md).  
  
- **Modificatori combinati.** Non è possibile specificare `Static` insieme a `ReadOnly` , `Shadows` o `Shared` nella stessa dichiarazione.  
  
## <a name="behavior"></a>Comportamento  
 Quando si dichiara una variabile statica in una `Shared` routine, solo una copia della variabile statica è disponibile per l'intera applicazione. È possibile chiamare una `Shared` stored procedure usando il nome della classe, non una variabile che punta a un'istanza della classe.  
  
 Quando si dichiara una variabile statica in una routine che non è `Shared` , solo una copia della variabile è disponibile per ogni istanza della classe. Una routine non condivisa viene chiamata utilizzando una variabile che punta a un'istanza specifica della classe.  
  
## <a name="example"></a>Esempio  
 L'esempio seguente illustra l'uso di `Static`.  
  
 [!code-vb[VbVbalrKeywords#5](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrKeywords/VB/Class1.vb#5)]  
  
 La `Static` variabile `totalSales` viene inizializzata su 0 solo una volta. Ogni volta che si immette `updateSales` , `totalSales` dispone ancora del valore più recente calcolato.  
  
 Il `Static` modificatore può essere usato in questo contesto:  
  
 [Istruzione Dim](../statements/dim-statement.md)  
  
## <a name="see-also"></a>Vedere anche

- [Shadows](shadows.md)
- [Condivisa](shared.md)
- [Durata in Visual Basic](../../programming-guide/language-features/declared-elements/lifetime.md)
- [Dichiarazione di variabile](../../programming-guide/language-features/variables/variable-declaration.md)
- [Strutture](../../programming-guide/language-features/data-types/structures.md)
- [Inferenza del tipo di variabile locale](../../programming-guide/language-features/variables/local-type-inference.md)
- [Oggetti e classi](../../programming-guide/language-features/objects-and-classes/index.md)
