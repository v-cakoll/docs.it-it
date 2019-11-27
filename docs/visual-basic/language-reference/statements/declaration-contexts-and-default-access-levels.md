---
title: Contesti delle dichiarazioni e livelli di accesso predefiniti
ms.date: 07/20/2015
helpviewer_keywords:
- module level, defined
- declaration contexts, Visual Basic
- procedure level, defined
- namespace level, defined
- access levels, Visual Basic
- access levels, default levels
ms.assetid: bf63b96e-e825-4745-88c8-5dae222728db
ms.openlocfilehash: 1ba25d830b1e7529bdf09c1195cc1fe7f9b2243b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74354095"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contesti delle dichiarazioni e livelli di accesso predefiniti (Visual Basic)
Questo argomento descrive quali tipi di Visual Basic possono essere dichiarati all'interno di altri tipi e quali sono i livelli di accesso predefiniti se non specificati.  
  
## <a name="declaration-context-levels"></a>Livelli del contesto di dichiarazione  
 Il *contesto di dichiarazione* di un elemento di programmazione è l'area di codice in cui viene dichiarata. Si tratta spesso di un altro elemento di programmazione, che viene quindi denominato *elemento contenitore*.  
  
 I livelli dei contesti di dichiarazione sono i seguenti:  
  
- *Livello dello spazio dei nomi* , all'interno di un file di origine o di uno spazio dei nomi, ma non all'interno di una classe, struttura, modulo  
  
- *Livello del modulo* , all'interno di una classe, struttura, modulo o interfaccia ma non all'interno di una routine o un blocco  
  
- *Livello di routine* : all'interno di una routine o di un blocco (ad esempio `If` o `For`)  
  
 La tabella seguente illustra i livelli di accesso predefiniti per vari elementi di programmazione dichiarati, a seconda dei contesti di dichiarazione.  
  
|Elemento dichiarato|Livello dello spazio dei nomi|Livello modulo|Livello di routine|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([istruzione Dim](../../../visual-basic/language-reference/statements/dim-statement.md))|Non consentito|`Private` (`Public` in `Structure`, non consentito in `Interface`)|`Public`|  
|Constant ([istruzione Const](../../../visual-basic/language-reference/statements/const-statement.md))|Non consentito|`Private` (`Public` in `Structure`, non consentito in `Interface`)|`Public`|  
|Enumeration ([istruzione enum](../../../visual-basic/language-reference/statements/enum-statement.md))|`Friend`|`Public`|Non consentito|  
|Classe ([istruzione di classe](../../../visual-basic/language-reference/statements/class-statement.md))|`Friend`|`Public`|Non consentito|  
|Structure ([istruzione Structure](../../../visual-basic/language-reference/statements/structure-statement.md))|`Friend`|`Public`|Non consentito|  
|Module ([istruzione modulo](../../../visual-basic/language-reference/statements/module-statement.md))|`Friend`|Non consentito|Non consentito|  
|Interface ([istruzione Interface](../../../visual-basic/language-reference/statements/interface-statement.md))|`Friend`|`Public`|Non consentito|  
|Routine ([istruzione Function](../../../visual-basic/language-reference/statements/function-statement.md), [istruzione Sub](../../../visual-basic/language-reference/statements/sub-statement.md))|Non consentito|`Public`|Non consentito|  
|Riferimento esterno ([istruzione Declare](../../../visual-basic/language-reference/statements/declare-statement.md))|Non consentito|`Public` (non consentito in `Interface`)|Non consentito|  
|Operatore operator ([istruzione](../../../visual-basic/language-reference/statements/operator-statement.md))|Non consentito|`Public` (non consentito in `Interface` o `Module`)|Non consentito|  
|Property ([istruzione Property](../../../visual-basic/language-reference/statements/property-statement.md))|Non consentito|`Public`|Non consentito|  
|Proprietà predefinita ([impostazione predefinita](../../../visual-basic/language-reference/modifiers/default.md))|Non consentito|`Public` (non consentito in `Module`)|Non consentito|  
|Event ([istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md))|Non consentito|`Public`|Non consentito|  
|Delegate ([istruzione Delegate](../../../visual-basic/language-reference/statements/delegate-statement.md))|`Friend`|`Public`|Non consentito|  
  
 Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../../visual-basic/programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche

- [Friend](../../../visual-basic/language-reference/modifiers/friend.md)
- [Private](../../../visual-basic/language-reference/modifiers/private.md)
- [Public](../../../visual-basic/language-reference/modifiers/public.md)
