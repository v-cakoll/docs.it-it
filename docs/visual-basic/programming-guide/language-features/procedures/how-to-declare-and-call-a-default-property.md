---
title: 'Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic'
ms.date: 07/20/2015
helpviewer_keywords:
- defaults [Visual Basic], properties
- properties [Visual Basic], default
- procedures [Visual Basic], defining
- default properties [Visual Basic], in Visual Basic
- Visual Basic code, procedures
- Visual Basic code, properties
- default properties
ms.assetid: 68b4026e-09ef-4613-808e-f6287494ff63
ms.openlocfilehash: f11b5a184b72df68e302094dee762ec6876a397c
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58829330"
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Procedura: Dichiarare e chiamare una proprietà predefinita in Visual Basic
Oggetto *predefiniti delle proprietà* è una proprietà di classe o struttura che il codice possa accedere senza specificarla. Quando si chiama codice nomi una classe o struttura, ma non una proprietà e il contesto consente l'accesso a una proprietà, Visual Basic viene risolto l'accesso a tale classe o una proprietà predefinita della struttura, se disponibile.  
  
 Una classe o struttura può avere al massimo una proprietà predefinita. Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e avere più di una versione di esso.  
  
 Per altre informazioni, vedere [predefinito](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Per dichiarare una proprietà predefinita  
  
1.  Dichiarare la proprietà in modo normale. Non si specifica la `Shared` o `Private` (parola chiave).  
  
2.  Includere il `Default` parola chiave nella dichiarazione di proprietà.  
  
3.  Specificare almeno un parametro per la proprietà. È possibile definire una proprietà predefinita che non accetta almeno un argomento.  
  
     [!code-vb[VbVbcnProcedures#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#17)]  
  
### <a name="to-call-a-default-property"></a>Per chiamare una proprietà predefinita  
  
1.  Dichiarare una variabile del tipo di classe o struttura che lo contiene.  
  
     [!code-vb[VbVbcnProcedures#16](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#16)]  
  
2.  Usare il nome della variabile da solo in un'espressione in cui è in genere necessario includere il nome della proprietà.  
  
     [!code-vb[VbVbcnProcedures#21](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#21)]  
  
3.  Seguire il nome della variabile con un elenco di argomenti racchiuso tra parentesi. Una proprietà predefinita deve accettare almeno un argomento.  
  
     [!code-vb[VbVbcnProcedures#20](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#20)]  
  
4.  Per recuperare il valore della proprietà predefinito, usare il nome di variabile con un elenco di argomenti, in un'espressione o in seguito uguali (`=`) Accedi a un'istruzione di assegnazione.  
  
     [!code-vb[VbVbcnProcedures#15](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#15)]  
  
5.  Per impostare il valore della proprietà predefinito, usare il nome di variabile con un elenco di argomenti, sul lato sinistro di un'istruzione di assegnazione.  
  
     [!code-vb[VbVbcnProcedures#14](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#14)]  
  
6.  È sempre possibile specificare il nome della proprietà predefinita con il nome della variabile, esattamente come si farebbe per accedere a qualsiasi altra proprietà.  
  
     [!code-vb[VbVbcnProcedures#19](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#19)]  
  
## <a name="example"></a>Esempio  
 L'esempio seguente dichiara una proprietà predefinita in una classe.  
  
 [!code-vb[VbVbcnProcedures#12](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#12)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1`. Le tre istruzioni di assegnazione valori memorizzati in `myProperty`e il <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata legge i valori.  
  
 [!code-vb[VbVbcnProcedures#13](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#13)]  
  
 L'uso più comune di una proprietà predefinita è il <xref:Microsoft.VisualBasic.Collection.Item%2A> proprietà in varie classi di raccolta.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma è possibile rendere il codice più difficile da leggere. Se il codice chiamante non abbia familiarità con la classe o struttura, quando effettua un riferimento al nome della classe o struttura non può essere determinato se il riferimento accede la classe o struttura stessa o una proprietà predefinita. Questo può causare errori del compilatore o meno evidenti in fase di esecuzione della logica.  
  
 In qualche modo, è possibile ridurre le probabilità di errori di proprietà predefiniti utilizzando sempre la [Option Strict Statement](../../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo del compilatore controllo `On`.  
  
 Se si prevede di usare una struttura o classe predefinite nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, quali il nome sarà.  
  
 A causa di questi svantaggi, è necessario considerare che non definisce le proprietà predefinite. Per la leggibilità del codice, è necessario considerare anche fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.  
  
## <a name="see-also"></a>Vedere anche

- [Routine Property](./property-procedures.md)
- [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)
- [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)
- [Default](../../../../visual-basic/language-reference/modifiers/default.md)
- [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)
- [Procedura: Creare una proprietà](./how-to-create-a-property.md)
- [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)
- [Procedura: Chiamare una routine Property](./how-to-call-a-property-procedure.md)
- [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)
- [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
