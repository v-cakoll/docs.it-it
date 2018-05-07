---
title: Contesti delle dichiarazioni e livelli di accesso predefiniti (Visual Basic)
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: b30b1068fe662d5f0318a1712dc4690b79bd739d
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contesti delle dichiarazioni e livelli di accesso predefiniti (Visual Basic)
Questo argomento descrive i tipi di Visual Basic possono essere dichiarati all'interno di altri tipi e cosa i livelli di accesso per impostazione predefinita se non diversamente specificato.  
  
## <a name="declaration-context-levels"></a>Livelli di contesto di dichiarazione  
 Il *contesto della dichiarazione* di un elemento di programmazione è l'area di codice in cui viene dichiarato. Spesso si tratta di un altro elemento di programmazione, viene quindi chiamato il *contenente l'elemento*.  
  
 I livelli di contesti delle dichiarazioni sono i seguenti:  
  
-   *Livello Namespace* , all'interno di un file di origine o dello spazio dei nomi ma non all'interno di una classe, struttura, modulo o interfaccia  
  
-   *Livello di modulo* , all'interno di una classe, struttura, modulo o interfaccia ma non all'interno di una stored procedure o un blocco  
  
-   *Livello di routine* , all'interno di una stored procedure o un blocco (ad esempio `If` o `For`)  
  
 Nella tabella seguente mostra i livelli di accesso predefinito per i vari elementi di programmazione dichiarati, a seconda della loro contesti delle dichiarazioni.  
  
|Elemento dichiarato|Livello Namespace|Livello di modulo|Livello di routine|  
|----------------------|---------------------|------------------|---------------------|  
|Variabile ([istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|Non è consentito|`Private` (`Public` in `Structure`, non consentito in `Interface`)|`Public`|  
|Costante ([Const (istruzione)](../../../visual-basic/language-reference/statements/const-statement.md))|Non è consentito|`Private` (`Public` in `Structure`, non consentito in `Interface`)|`Public`|  
|Enumerazione ([istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Non è consentito|  
|Classe ([istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Non è consentito|  
|Struttura ([struttura istruzione](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Non è consentito|  
|Modulo ([istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Non è consentito|Non è consentito|  
|Interfaccia ([istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Non è consentito|  
|Procedure ([istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md), [istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md))|Non è consentito|`Public`|Non è consentito|  
|Riferimento esterno ([istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md))|Non è consentito|`Public` (non consentito in `Interface`)|Non è consentito|  
|Operatore ([Operator (istruzione)](../../../visual-basic/language-reference/statements/operator-statement.md))|Non è consentito|`Public` (non consentito in `Interface` o `Module`)|Non è consentito|  
|Proprietà ([istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md))|Non è consentito|`Public`|Non è consentito|  
|Proprietà predefinita ([predefinito](../../../visual-basic/language-reference/modifiers/default.md))|Non è consentito|`Public` (non consentito in `Module`)|Non è consentito|  
|Eventi ([istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md))|Non è consentito|`Public`|Non è consentito|  
|Delegato ([istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Non è consentito|  
  
 Per ulteriori informazioni, vedere [accedere livelli in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche  
 [Friend](../../../visual-basic/language-reference/modifiers/friend.md)  
 [Private](../../../visual-basic/language-reference/modifiers/private.md)  
 [Public](../../../visual-basic/language-reference/modifiers/public.md)
