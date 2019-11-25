---
title: Istruzione AddHandler
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: c110116af75d4fb39c016b8d6afcdb707fa6599b
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350183"
---
# <a name="addhandler-statement"></a>Istruzione AddHandler
Associates an event with an event handler at run time.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
|||
|---|---|
|event|The name of the event to handle.|  
|`eventhandler`|The name of a procedure that handles the event.|
|||
  
## <a name="remarks"></a>Note  
 The `AddHandler` and `RemoveHandler` statements allow you to start and stop event handling at any time during program execution.  
  
 The signature of the `eventhandler` procedure must match the signature of the event `event`.  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. For more information, see [Handles](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
> For custom events, the `AddHandler` statement invokes the event's `AddHandler` accessor. For more information on custom events, see [Event Statement](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
