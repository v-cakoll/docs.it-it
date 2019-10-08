---
title: Istruzione AddHandler (Visual Basic)
ms.date: 07/20/2015
f1_keywords:
- vb.AddHandlerMethod
- addhandler
- vb.addhandler
helpviewer_keywords:
- AddHandler statement [Visual Basic]
ms.assetid: cfe69799-2a0f-42c0-a99e-09fed954da01
ms.openlocfilehash: 95277f532488b0cf56114e5ee94dc3528e3a2e02
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72004534"
---
# <a name="addhandler-statement"></a>Istruzione AddHandler
Associa un evento a un gestore eventi in fase di esecuzione.  
  
## <a name="syntax"></a>Sintassi  
  
```vb  
AddHandler event, AddressOf eventhandler  
```  
  
## <a name="parts"></a>Parti  
|||
|---|---|
|event|Nome dell'evento da gestire.|  
|`eventhandler`|Nome di una routine che gestisce l'evento.|
|||
  
## <a name="remarks"></a>Note  
 Le istruzioni `AddHandler` e `RemoveHandler` consentono di avviare e arrestare la gestione degli eventi in qualsiasi momento durante l'esecuzione del programma.  
  
 La firma della procedura `eventhandler` deve corrispondere alla firma dell'evento `event`.  
  
 La parola chiave `Handles` e l'istruzione `AddHandler` consentono entrambe di specificare che quelle particolari routine gestiscono particolari eventi, ma esistono alcune differenze. L'istruzione `AddHandler` connette le routine agli eventi in fase di esecuzione. Usare la parola chiave `Handles` quando si definisce una routine, per specificare che questa gestisce un particolare evento. Per ulteriori informazioni, vedere [handle](../../../visual-basic/language-reference/statements/handles-clause.md).  
  
> [!NOTE]
> Per gli eventi personalizzati, l'istruzione `AddHandler` richiama la funzione di accesso `AddHandler` dell'evento. Per ulteriori informazioni sugli eventi personalizzati, vedere [istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md).  
  
## <a name="example"></a>Esempio  
 [!code-vb[VbVbalrEvents#17](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrEvents/VB/Class1.vb#17)]  
  
## <a name="see-also"></a>Vedere anche

- [Istruzione RemoveHandler](../../../visual-basic/language-reference/statements/removehandler-statement.md)
- [Handles](../../../visual-basic/language-reference/statements/handles-clause.md)
- [Istruzione Event](../../../visual-basic/language-reference/statements/event-statement.md)
- [Eventi](../../../visual-basic/programming-guide/language-features/events/index.md)
