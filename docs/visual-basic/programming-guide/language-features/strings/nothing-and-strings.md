---
title: Nothing e stringhe
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: 392de45b0ee1688224f3e8170b0144f1acdb0912
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84360566"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Comportamento di Nothing con le stringhe in Visual Basic
Il runtime di Visual Basic e il .NET Framework `Nothing` vengono valutati in modo diverso per le stringhe.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Visual Basic Runtime e il .NET Framework  
 Prendere in considerazione gli esempi seguenti:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Il runtime di Visual Basic in genere restituisce `Nothing` una stringa vuota (""). Il .NET Framework non, tuttavia, genera un'eccezione ogni volta che viene eseguito un tentativo di eseguire un'operazione di stringa su `Nothing` .  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle stringhe in Visual Basic](introduction-to-strings.md)
