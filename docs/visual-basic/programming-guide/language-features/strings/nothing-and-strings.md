---
title: Comportamento di Nothing con le stringhe in Visual Basic
ms.date: 07/20/2015
helpviewer_keywords:
- strings [Visual Basic], Nothing
ms.assetid: 261380af-2024-4ecf-823b-43b1034d92cd
ms.openlocfilehash: f5c1ea8cc0728b25e8e874963967aed504e466d7
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65591349"
---
# <a name="nothing-and-strings-in-visual-basic"></a>Comportamento di Nothing con le stringhe in Visual Basic
Il runtime di Visual Basic e .NET Framework valutare `Nothing` in modo diverso quando si tratta di stringhe.  
  
## <a name="visual-basic-runtime-and-the-net-framework"></a>Runtime di Visual Basic e .NET Framework  
 Si consideri l'esempio seguente:  
  
 [!code-vb[VbVbalrStrings#47](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrStrings/VB/Class2.vb#47)]  
  
 Il runtime di Visual Basic restituisce in genere `Nothing` come una stringa vuota (""). .NET Framework non lo fa, tuttavia e genera un'eccezione ogni volta che viene effettuato un tentativo di eseguire un'operazione di stringa su `Nothing`.  
  
## <a name="see-also"></a>Vedere anche

- [Introduzione alle stringhe in Visual Basic](../../../../visual-basic/programming-guide/language-features/strings/introduction-to-strings.md)
