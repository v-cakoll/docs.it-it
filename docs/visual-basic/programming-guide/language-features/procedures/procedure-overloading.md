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
ms.openlocfilehash: 0d1f2c4d8c88922659b3d91ed41d5e760e6e5233
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33653914"
---
# <a name="procedure-overloading-visual-basic"></a>Overload della routine (Visual Basic)
*L'overload* significa che una stored procedure che sia necessario definirlo in più versioni, utilizzando lo stesso nome ma gli elenchi di parametri diversi. Lo scopo dell'overload consiste nel definire più versioni strettamente correlate di una stored procedure senza la necessità di distinguere per nome. Questo caso variando l'elenco di parametri.  
  
## <a name="overloading-rules"></a>Regole di overload  
 Quando si esegue l'overload di una stored procedure, si applicano le regole seguenti:  
  
-   **Stesso nome**. Ogni versione di overload è necessario utilizzare lo stesso nome di stored procedure.  
  
-   **Firma diversa**. Ogni versione di overload deve essere diverso da tutte le altre versioni di overload in almeno uno dei seguenti:  
  
    -   Numero di parametri  
  
    -   Ordine dei parametri  
  
    -   Tipi di dati dei parametri  
  
    -   Numero di parametri di tipo (per una routine generica)  
  
    -   Tipo restituito (solo per un operatore di conversione)  
  
     Il nome della routine, insieme a elementi precedenti collettivamente denominati il *firma* della procedura. Quando si chiama una routine di overload, il compilatore utilizza la firma per verificare che la chiamata corrisponda in modo corretto la definizione.  
  
-   **Elementi che non fanno parte della firma**. È possibile eseguire l'overload di una stored procedure senza modificare la firma. In particolare, è possibile eseguire l'overload di una routine modificando solo uno o più dei seguenti elementi:  
  
    -   Parole chiave di modificatore di routine, ad esempio `Public`, `Shared`, e `Static`  
  
    -   Nomi dei parametri di parametro o tipo  
  
    -   Vincoli del parametro di tipo (per una routine generica)  
  
    -   Parole chiave di modificatori di parametro, ad esempio `ByRef` e `Optional`  
  
    -   Se viene restituito un valore  
  
    -   Il tipo di dati del valore restituito (ad eccezione di un operatore di conversione)  
  
     Gli elementi nell'elenco precedente non fanno parte della firma. Anche se non possono essere utilizzati per distinguere tra le versioni di overload, è possibile variare tra le versioni di overload che si differenzino correttamente per le firme.  
  
-   **Associazione tardiva argomenti**. Se si prevede di passare una variabile oggetto ad associazione tardiva a una versione di overload, è necessario dichiarare il parametro appropriato come <xref:System.Object>.  
  
## <a name="multiple-versions-of-a-procedure"></a>Più versioni di una stored Procedure  
 Si supponga che si sta scrivendo un `Sub` procedura per inviare una transazione saldo di un cliente e si desidera essere in grado di riferire al cliente in base al nome o numero di conto. A tale scopo, è possibile definire due diversi `Sub` procedure, come nell'esempio seguente:  
  
 [!code-vb[VbVbcnProcedures#73](./codesnippet/VisualBasic/procedure-overloading_1.vb)]  
  
### <a name="overloaded-versions"></a>Versioni di overload  
 In alternativa è possibile eseguire l'overload di un singolo nome di routine. È possibile utilizzare il [overload](../../../../visual-basic/language-reference/modifiers/overloads.md) (parola chiave) per definire una versione della procedura per ogni elenco di parametri, come indicato di seguito:  
  
 [!code-vb[VbVbcnProcedures#72](./codesnippet/VisualBasic/procedure-overloading_2.vb)]  
  
#### <a name="additional-overloads"></a>Overload aggiuntivi  
 Se si desidera accettare un importo di transazione in uno `Decimal` o `Single`, inoltre, è possibile eseguire l'overload `post` per consentire questa variante. Se viene eseguita questa operazione per ognuno degli overload nell'esempio precedente, sarebbe necessario quattro `Sub` procedure, tutte con lo stesso nome ma con quattro firme diverse.  
  
## <a name="advantages-of-overloading"></a>Vantaggi dell'overload  
 Il vantaggio di overload di una routine è la flessibilità della chiamata. Utilizzare il `post` routine dichiarata nell'esempio precedente, il codice chiamante può ottenere l'identificazione del cliente come un `String` o `Integer`e quindi chiamare la stessa procedura in entrambi i casi. Questa condizione è illustrata nell'esempio che segue.  
  
 [!code-vb[VbVbcnProcedures#56](./codesnippet/VisualBasic/procedure-overloading_3.vb)]  
  
 [!code-vb[VbVbcnProcedures#57](./codesnippet/VisualBasic/procedure-overloading_4.vb)]  
  
## <a name="see-also"></a>Vedere anche  
 [Routine](./index.md)  
 [Procedura: Definire più versioni di una routine](./how-to-define-multiple-versions-of-a-procedure.md)  
 [Procedura: Chiamare una routine di overload](./how-to-call-an-overloaded-procedure.md)  
 [Procedura: Eseguire l'overload di una routine che accetta parametri facoltativi](./how-to-overload-a-procedure-that-takes-optional-parameters.md)  
 [Procedura: Eseguire l'overload di una routine che accetta un numero indefinito di parametri](./how-to-overload-a-procedure-that-takes-an-indefinite-number-of-parameters.md)  
 [Considerazioni sull'overload di routine](./considerations-in-overloading-procedures.md)  
 [Risoluzione dell'overload](./overload-resolution.md)  
 [Overload](../../../../visual-basic/language-reference/modifiers/overloads.md)  
 [Tipi generici in Visual Basic](../../../../visual-basic/programming-guide/language-features/data-types/generic-types.md)
