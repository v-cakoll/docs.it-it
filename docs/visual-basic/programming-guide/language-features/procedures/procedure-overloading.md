---
title: Overload della routine (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- signatures
- Overloads keyword [Visual Basic]
- hiding by signature
- Visual Basic code, procedures
- procedures [Visual Basic], signatures for
- procedures [Visual Basic], overloading
- procedures [Visual Basic], multiple versions
- parameters [Visual Basic], lists
- signatures [Visual Basic], procedure
- parameter lists [Visual Basic]
- Visual Basic code, parameter lists
- Shadows keyword [Visual Basic]
- procedure overloading
- procedures [Visual Basic], parameter lists
ms.assetid: fbc7fb18-e3b2-48b6-b554-64c00ed09d2a
ms.openlocfilehash: 6e8d1fa72c60c4fa3d2237ad24c2d1b4891a7bf2
ms.sourcegitcommit: bce0586f0cccaae6d6cbd625d5a7b824d1d3de4b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/02/2019
ms.locfileid: "58828238"
---
# <a name="procedure-overloading-visual-basic"></a>Overload della routine (Visual Basic)
*L'overload* significa che una routine di definirla in più versioni, usando lo stesso nome ma gli elenchi di parametri diversi. Lo scopo dell'overload consiste nel definire più versioni strettamente correlate di una stored procedure senza la necessità di distinguerli in base al nome. Eseguire questa operazione modificando l'elenco di parametri.  
  
## <a name="overloading-rules"></a>Regole di overload  
 Quando si esegue l'overload di una procedura, si applicano le regole seguenti:  
  
-   **Stesso nome**. Ogni versione di overload debba usare lo stesso nome di procedura.  
  
-   **Firma diversa**. Ogni versione di overload deve essere diversa da tutte le altre versioni di overload in almeno uno dei seguenti:  
  
    -   Numero di parametri  
  
    -   Ordine dei parametri  
  
    -   Tipi di dati dei parametri  
  
    -   Numero di parametri di tipo (per una routine generica)  
  
    -   Tipo restituito (solo per un operatore di conversione)  
  
     Con il nome della routine, degli elementi precedenti vengono collettivamente definiti il *firma* della procedura. Quando si chiama una routine di overload, il compilatore Usa la firma per verificare che la chiamata corrisponda in modo corretto la definizione.  
  
-   **Elementi che non fanno parte della firma**. È possibile eseguire l'overload di una procedura senza modificare la firma. In particolare, è possibile eseguire l'overload di una procedura variando solo uno o più dei seguenti elementi:  
  
    -   Parole chiave di modificatore di routine, ad esempio `Public`, `Shared`, e `Static`  
  
    -   Nomi dei parametri di parametro o tipo  
  
    -   Vincoli del parametro (per una routine generica)  
  
    -   Parole chiave di modificatori di parametro, ad esempio `ByRef` e `Optional`  
  
    -   Se viene restituito un valore  
  
    -   il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)  
  
     Gli elementi nell'elenco precedente non fanno parte della firma. Anche se non possono essere utilizzati per distinguere le versioni di overload, è possibile variare tra le versioni di overload che si differenziano in modo corretto per le firme.  
  
-   **Associazione tardiva argomenti**. Se si prevede di passare una variabile di oggetto associato ad associazione tardiva a una versione di overload, è necessario dichiarare il parametro appropriato come <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Più versioni di una stored Procedure  
 Si supponga che si sta scrivendo un `Sub` procedure per inserire una transazione con saldo di un cliente e si desidera essere in grado di fare riferimento al cliente in base al nome o dal numero di account. Di conseguenza, è possibile definire due diversi `Sub` procedure, come nell'esempio seguente:  
  
 [!code-vb[VbVbcnProcedures#73](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#73)]  
  
### <a name="overloaded-versions"></a>Versioni di overload  
 In alternativa è possibile eseguire l'overload di un singolo nome di routine. È possibile usare la [Overloads](../../../../visual-basic/language-reference/modifiers/overloads.md) parola chiave per definire una versione della procedura per ogni elenco di parametri, come indicato di seguito:  
  
 [!code-vb[VbVbcnProcedures#72](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#72)]  
  
#### <a name="additional-overloads"></a>Overload aggiuntivi  
 Se si vuole accettare un importo di transazione in uno `Decimal` oppure `Single`, è possibile eseguire l'overload ulteriormente `post` per consentire questa variazione. Se viene eseguita questa operazione per ogni overload nell'esempio precedente, sarebbe necessario quattro `Sub` procedure, tutte con lo stesso nome ma con quattro firme diverse.  
  
## <a name="advantages-of-overloading"></a>Vantaggi dell'overload  
 Il vantaggio di overload di una routine è la flessibilità della chiamata. Usare la `post` routine dichiarata nell'esempio precedente, il codice chiamante può ottenere l'identificazione del cliente come un `String` o un `Integer`, quindi chiamare la stessa procedura in entrambi i casi. Questa condizione è illustrata nell'esempio che segue.  
  
 [!code-vb[VbVbcnProcedures#56](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#56)]  
  
 [!code-vb[VbVbcnProcedures#57](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbcnProcedures/VB/Class1.vb#57)]  
  
## <a name="see-also"></a>Vedere anche

- [Routine](./index.md)
- [Procedura: Definire più versioni di una stored Procedure](./how-to-define-multiple-versions-of-a-procedure.md)
- [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)
- [Procedura: Overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)
- [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)
- [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)
- [Risoluzione dell'overload](./overload-resolution.md)
- [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)
- [Generic Types in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
