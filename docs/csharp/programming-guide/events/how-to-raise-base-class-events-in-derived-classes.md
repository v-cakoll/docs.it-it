---
title: Come generare eventi di classe base nelle classi derivate-guida per programmatori C#
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: e2d2dfc2809a4de1756bfc362880eebc79076b94
ms.sourcegitcommit: a241301495a84cc8c64fe972330d16edd619868b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/01/2020
ms.locfileid: "84240629"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a>Come generare eventi di classe base nelle classi derivate (Guida per programmatori C#)
L'esempio seguente illustra il metodo standard di dichiarazione degli eventi in una classe base in modo che possano essere generati anche dalle classi derivate. Questo modello viene ampiamente usato nelle classi Windows Forms nelle librerie di classi .NET.  
  
 Quando si crea una classe che può essere usata come classe base di altre classi, è necessario tenere presente che gli eventi sono un tipo speciale di delegati che possono essere richiamati solo dall'interno della classe che li ha dichiarati. Le classi derivate non possono richiamare direttamente gli eventi dichiarati all'interno della classe base. Nonostante sia necessario a volte un evento che possa essere generato solo dalla classe base, nella maggior parte dei casi è opportuno consentire alla classe derivata di richiamare eventi della classe base. A tale scopo, è possibile creare un metodo di chiamata protetto nella classe base che esegue il wrapping dell'evento. Le classi derivate possono richiamare indirettamente l'evento richiamando o eseguendo l'override di questo metodo di chiamata.  
  
> [!NOTE]
> Non dichiarare eventi virtuali in una classe base ed eseguire l'override in una classe derivata. Il compilatore C# non è in grado di gestirli correttamente e non è possibile prevedere se un sottoscrittore dell'evento derivato sottoscriverà effettivamente l'evento della classe base.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../index.md)
- [Events](./index.md)
- [Delegati](../delegates/index.md)
- [Modificatori di accesso](../classes-and-structs/access-modifiers.md)
- [Creazione di gestori eventi in Windows Form](../../../framework/winforms/creating-event-handlers-in-windows-forms.md)
