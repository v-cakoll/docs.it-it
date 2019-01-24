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
ms.openlocfilehash: 75c5b16164e9ecb6558e445c59e4a312158ff4f8
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54580811"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contesti delle dichiarazioni e livelli di accesso predefiniti (Visual Basic)
Questo argomento descrive i tipi di Visual Basic possono essere dichiarati all'interno di altri tipi, e ciò che i livelli di accesso per impostazione predefinita se non diversamente specificato.  
  
## <a name="declaration-context-levels"></a>Livelli dei contesti di dichiarazione  
 Il *contesto della dichiarazione* di un elemento di programmazione è l'area di codice in cui è dichiarata. Si tratta spesso di un altro elemento di programmazione, che viene quindi chiamato il *contenente l'elemento*.  
  
 I livelli per contesti delle dichiarazioni sono i seguenti:  
  
-   *A livello di Namespace* , ovvero all'interno di un file di origine o lo spazio dei nomi ma non all'interno di una classe, struttura, modulo o interfaccia  
  
-   *Livello di modulo* , ovvero all'interno di una classe, struttura, modulo o interfaccia, ma non all'interno di una routine o un blocco  
  
-   *Livello di routine* , ovvero all'interno di una routine o un blocco (ad esempio `If` o `For`)  
  
 La tabella seguente illustra i livelli di accesso predefinito per vari elementi di programmazione dichiarati, a seconda della loro contesti delle dichiarazioni.  
  
|Elemento dichiarato|A livello di Namespace|Livello di modulo|Livello di routine|  
|----------------------|---------------------|------------------|---------------------|  
|Variabili ([istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|Non è consentita|`Private` (`Public` nelle `Structure`, non consentito in `Interface`)|`Public`|  
|Costante ([Const (istruzione)](../../../visual-basic/language-reference/statements/const-statement.md))|Non è consentita|`Private` (`Public` nelle `Structure`, non consentito in `Interface`)|`Public`|  
|Enumerazione ([istruzione Enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Non è consentita|  
|Classe ([istruzione Class](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Non è consentita|  
|Struttura ([struttura istruzione](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Non è consentita|  
|Modulo ([istruzione Module](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Non è consentita|Non è consentita|  
|Interfaccia ([istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Non è consentita|  
|Procedure ([istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md), [istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md))|Non è consentita|`Public`|Non è consentita|  
|Riferimento esterno ([Declare Statement](../../../visual-basic/language-reference/statements/declare-statement.md))|Non è consentita|`Public` (non consentito in `Interface`)|Non è consentita|  
|Operatore ([Operator Statement](../../../visual-basic/language-reference/statements/operator-statement.md))|Non è consentita|`Public` (non consentito nelle `Interface` o `Module`)|Non è consentita|  
|Proprietà ([Property Statement](../../../visual-basic/language-reference/statements/property-statement.md))|Non è consentita|`Public`|Non è consentita|  
|Proprietà predefinita ([predefinito](../../../visual-basic/language-reference/modifiers/default.md))|Non è consentita|`Public` (non consentito in `Module`)|Non è consentita|  
|Evento ([istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md))|Non è consentita|`Public`|Non è consentita|  
|Delegato ([istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Non è consentita|  
  
 Per altre informazioni, vedere [Access levels in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche
- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
