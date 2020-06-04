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
ms.openlocfilehash: b5bb943a062ac648f88645fb6de1acb42213071c
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84404797"
---
# <a name="declaration-contexts-and-default-access-levels-visual-basic"></a>Contesti delle dichiarazioni e livelli di accesso predefiniti (Visual Basic)
Questo argomento descrive quali tipi di Visual Basic possono essere dichiarati all'interno di altri tipi e quali sono i livelli di accesso predefiniti se non specificati.  
  
## <a name="declaration-context-levels"></a>Livelli del contesto di dichiarazione  
 Il *contesto di dichiarazione* di un elemento di programmazione è l'area di codice in cui viene dichiarata. Si tratta spesso di un altro elemento di programmazione, che viene quindi denominato *elemento contenitore*.  
  
 I livelli dei contesti di dichiarazione sono i seguenti:  
  
- *Livello dello spazio dei nomi* , all'interno di un file di origine o di uno spazio dei nomi, ma non all'interno di una classe, struttura, modulo  
  
- *Livello del modulo* , all'interno di una classe, struttura, modulo o interfaccia ma non all'interno di una routine o un blocco  
  
- *Livello di routine* : all'interno di una routine o di un blocco (ad esempio `If` o `For` )  
  
 La tabella seguente illustra i livelli di accesso predefiniti per vari elementi di programmazione dichiarati, a seconda dei contesti di dichiarazione.  
  
|Elemento dichiarato|Livello dello spazio dei nomi|Livello modulo|Livello di routine|  
|----------------------|---------------------|------------------|---------------------|  
|Variable ([istruzione Dim](dim-statement.md))|Non consentito|`Private`( `Public` in `Structure` , non consentito in `Interface` )|`Public`|  
|Constant ([istruzione Const](const-statement.md))|Non consentito|`Private`( `Public` in `Structure` , non consentito in `Interface` )|`Public`|  
|Enumeration ([istruzione enum](enum-statement.md))|`Friend`|`Public`|Non consentito|  
|Classe ([istruzione di classe](class-statement.md))|`Friend`|`Public`|Non consentito|  
|Structure ([istruzione Structure](structure-statement.md))|`Friend`|`Public`|Non consentito|  
|Module ([istruzione modulo](module-statement.md))|`Friend`|Non consentito|Non consentito|  
|Interface ([istruzione Interface](interface-statement.md))|`Friend`|`Public`|Non consentito|  
|Routine ([istruzione Function](function-statement.md), [istruzione Sub](sub-statement.md))|Non consentito|`Public`|Non consentito|  
|Riferimento esterno ([istruzione Declare](declare-statement.md))|Non consentito|`Public`(non consentito in `Interface` )|Non consentito|  
|Operatore operator ([istruzione](operator-statement.md))|Non consentito|`Public`(non consentito in `Interface` o `Module` )|Non consentito|  
|Property ([istruzione Property](property-statement.md))|Non consentito|`Public`|Non consentito|  
|Proprietà predefinita ([impostazione predefinita](../modifiers/default.md))|Non consentito|`Public`(non consentito in `Module` )|Non consentito|  
|Event ([istruzione Event](event-statement.md))|Non consentito|`Public`|Non consentito|  
|Delegate ([istruzione Delegate](delegate-statement.md))|`Friend`|`Public`|Non consentito|  
  
 Per altre informazioni, vedere [livelli di accesso in Visual Basic](../../programming-guide/language-features/declared-elements/access-levels.md).  
  
## <a name="see-also"></a>Vedere anche

- [Amico](../modifiers/friend.md)
- [Privata](../modifiers/private.md)
- [Pubblica](../modifiers/public.md)
