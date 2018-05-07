---
title: 'Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic'
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
ms.openlocfilehash: 7805ee4dcd4bad0d0624c97ccc25232e9bc31ba4
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-declare-and-call-a-default-property-in-visual-basic"></a>Procedura: dichiarare e chiamare una proprietà predefinita in Visual Basic
Oggetto *proprietà predefinita* è una proprietà di classe o struttura che il codice può accedere senza specificarla. Quando si chiama codice nomi una classe o struttura ma non una proprietà e il contesto consente l'accesso a una proprietà, Visual Basic viene risolto l'accesso a tale classe o una proprietà predefinita della struttura, se disponibile.  
  
 Una classe o struttura può contenere al massimo una proprietà predefinita. Tuttavia, è possibile eseguire l'overload di una proprietà predefinita e più di una versione di esso.  
  
 Per ulteriori informazioni, vedere [predefinito](../../../../visual-basic/language-reference/modifiers/default.md).  
  
### <a name="to-declare-a-default-property"></a>Per dichiarare una proprietà predefinita  
  
1.  Dichiarare la proprietà in modo normale. Non si specifica il `Shared` o `Private` (parola chiave).  
  
2.  Includere il `Default` parola chiave nella dichiarazione di proprietà.  
  
3.  Specificare almeno un parametro per la proprietà. È possibile definire una proprietà predefinita che non accetta almeno un argomento.  
  
     [!code-vb[VbVbcnProcedures#17](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_1.vb)]  
  
### <a name="to-call-a-default-property"></a>Per chiamare una proprietà predefinita  
  
1.  Dichiarare una variabile del tipo di classe o struttura contenitore.  
  
     [!code-vb[VbVbcnProcedures#16](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_2.vb)]  
  
2.  Utilizzare il nome della variabile da solo in un'espressione in cui è in genere necessario includere il nome della proprietà.  
  
     [!code-vb[VbVbcnProcedures#21](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_3.vb)]  
  
3.  Seguire il nome della variabile con un elenco di argomenti tra parentesi. Una proprietà predefinita deve accettare almeno un argomento.  
  
     [!code-vb[VbVbcnProcedures#20](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_4.vb)]  
  
4.  Per recuperare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti, in un'espressione o in seguito uguali (`=`) eseguire l'accesso in un'istruzione di assegnazione.  
  
     [!code-vb[VbVbcnProcedures#15](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_5.vb)]  
  
5.  Per impostare il valore della proprietà predefinito, utilizzare il nome di variabile con un elenco di argomenti sul lato sinistro di un'istruzione di assegnazione.  
  
     [!code-vb[VbVbcnProcedures#14](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_6.vb)]  
  
6.  È sempre possibile specificare il nome predefinito della proprietà con il nome della variabile, così come si farebbe per accedere a qualsiasi altra proprietà.  
  
     [!code-vb[VbVbcnProcedures#19](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_7.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente dichiara una proprietà predefinita in una classe.  
  
 [!code-vb[VbVbcnProcedures#12](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_8.vb)]  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene illustrato come chiamare la proprietà predefinita `myProperty` sulla classe `class1`. Le istruzioni di assegnazione di tre valori memorizzati in `myProperty`e <xref:Microsoft.VisualBasic.Interaction.MsgBox%2A> chiamata legge i valori.  
  
 [!code-vb[VbVbcnProcedures#13](./codesnippet/VisualBasic/how-to-declare-and-call-a-default-property_9.vb)]  
  
 L'utilizzo più comune di una proprietà predefinita è la <xref:Microsoft.VisualBasic.Collection.Item%2A> proprietà in varie classi di raccolta.  
  
## <a name="robust-programming"></a>Programmazione efficiente  
 Proprietà predefinite può determinare un lieve riduzione del numero di caratteri del codice sorgente, ma può rendere più difficile la lettura di codice. Se il codice chiamante non ha familiarità con la classe o struttura, quando fa riferimento al nome di classe o struttura non può essere determinato se il riferimento accede la classe o struttura o una proprietà predefinita. Questo può causare errori del compilatore o meno evidenti della logica di runtime.  
  
 Piuttosto, è possibile ridurre il rischio di errori di proprietà predefiniti utilizzando sempre la [istruzione Option Strict](../../../../visual-basic/language-reference/statements/option-strict-statement.md) per impostare il tipo di compilatore controllo `On`.  
  
 Se si intende utilizzare una struttura o classe predefiniti nel codice, è necessario determinare se dispone di una proprietà predefinita e in tal caso, il relativo nome novità.  
  
 A causa di questi svantaggi, è consigliabile non definire proprietà predefinite. Per la leggibilità del codice, è necessario anche valutare fare sempre riferimento a tutte le proprietà in modo esplicito, anche le proprietà predefinite.  
  
## <a name="see-also"></a>Vedere anche  
 [Routine Property](./property-procedures.md)  
 [Parametri e argomenti delle routine](./procedure-parameters-and-arguments.md)  
 [Istruzione Property](../../../../visual-basic/language-reference/statements/property-statement.md)  
 [Default](../../../../visual-basic/language-reference/modifiers/default.md)  
 [Differenze tra proprietà e variabili in Visual Basic](./differences-between-properties-and-variables.md)  
 [Procedura: Creare una proprietà](./how-to-create-a-property.md)  
 [Procedura: Dichiarare una proprietà con livelli di accesso misti](./how-to-declare-a-property-with-mixed-access-levels.md)  
 [Procedura: Chiamare una routine di proprietà](./how-to-call-a-property-procedure.md)  
 [Procedura: Inserire un valore in una proprietà](./how-to-put-a-value-in-a-property.md)  
 [Procedura: Ottenere un valore da una proprietà](./how-to-get-a-value-from-a-property.md)
