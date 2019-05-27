---
title: 'Procedura: Generare eventi della classe di base in classi derivate - Guida per programmatori C#'
ms.custom: seodec18
ms.date: 07/20/2015
helpviewer_keywords:
- events [C#], in derived classes
ms.assetid: 2d20556a-0aad-46fc-845e-f85d86ea617a
ms.openlocfilehash: 2f200ff00534bde1fa0d016d64099e3ca28535a8
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65585853"
---
# <a name="how-to-raise-base-class-events-in-derived-classes-c-programming-guide"></a>Procedura: Generare eventi della classe di base in classi derivate (Guida per programmatori C#)
L'esempio seguente illustra il metodo standard di dichiarazione degli eventi in una classe base in modo che possano essere generati anche dalle classi derivate. Questo modello viene ampiamente usato nelle classi Windows Forms nella libreria di classi .NET Framework.  
  
 Quando si crea una classe che può essere usata come classe base di altre classi, è necessario tenere presente che gli eventi sono un tipo speciale di delegati che possono essere richiamati solo dall'interno della classe che li ha dichiarati. Le classi derivate non possono richiamare direttamente gli eventi dichiarati all'interno della classe base. Nonostante sia necessario a volte un evento che possa essere generato solo dalla classe base, nella maggior parte dei casi è opportuno consentire alla classe derivata di richiamare eventi della classe base. A tale scopo, è possibile creare un metodo di chiamata protetto nella classe base che esegue il wrapping dell'evento. Le classi derivate possono richiamare indirettamente l'evento richiamando o eseguendo l'override di questo metodo di chiamata.  
  
> [!NOTE]
>  Non dichiarare eventi virtuali in una classe base ed eseguire l'override in una classe derivata. Il compilatore C# non è in grado di gestirli correttamente e non è possibile prevedere se un sottoscrittore dell'evento derivato sottoscriverà effettivamente l'evento della classe base.  
  
## <a name="example"></a>Esempio  
 [!code-csharp[csProgGuideEvents#1](~/samples/snippets/csharp/VS_Snippets_VBCSharp/csProgGuideEvents/CS/Events.cs#1)]  
  
## <a name="see-also"></a>Vedere anche

- [Guida per programmatori C#](../../../csharp/programming-guide/index.md)
- [Eventi](../../../csharp/programming-guide/events/index.md)
- [Delegati](../../../csharp/programming-guide/delegates/index.md)
- [Modificatori di accesso](../../../csharp/programming-guide/classes-and-structs/access-modifiers.md)
- [Creazione di gestori eventi in Windows Form](../../../../docs/framework/winforms/creating-event-handlers-in-windows-forms.md)
