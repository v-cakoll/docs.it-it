---
title: 'Procedura: Gestire eventi di input utente nei controlli Windows Forms'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
- cpp
helpviewer_keywords:
- Windows Forms controls, user input
- user input [Windows Forms], Windows Forms controls
ms.assetid: 3de74dcf-fae3-42d0-92b5-bc04a61a6888
ms.openlocfilehash: ae230f22c929be39ea00eafe378c6910c4a9d35f
ms.sourcegitcommit: c7a7e1468bf0fa7f7065de951d60dfc8d5ba89f5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/14/2019
ms.locfileid: "65592092"
---
# <a name="how-to-handle-user-input-events-in-windows-forms-controls"></a><span data-ttu-id="fe0aa-102">Procedura: Gestire eventi di input utente nei controlli Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe0aa-102">How to: Handle User Input Events in Windows Forms Controls</span></span>
<span data-ttu-id="fe0aa-103">In questo esempio viene illustrato come gestire la maggior parte degli eventi di convalida, stato attivo, mouse e tastiera che possono verificarsi in un controllo Windows Form.</span><span class="sxs-lookup"><span data-stu-id="fe0aa-103">This example demonstrates how to handle most keyboard, mouse, focus, and validation events that can occur in a Windows Forms control.</span></span> <span data-ttu-id="fe0aa-104">La casella di testo denominata `TextBoxInput` riceve gli eventi quando è attiva e le informazioni relative a ogni evento vengono scritte nella casella di testo denominata `TextBoxOutput` nell'ordine di generazione degli eventi.</span><span class="sxs-lookup"><span data-stu-id="fe0aa-104">The text box named `TextBoxInput` receives the events when it has focus, and information about each event is written in the text box named `TextBoxOutput` in the order in which the events are raised.</span></span> <span data-ttu-id="fe0aa-105">L'applicazione include anche un set di caselle di controllo che possono essere usate per filtrare gli eventi da segnalare.</span><span class="sxs-lookup"><span data-stu-id="fe0aa-105">The application also includes a set of check boxes that can be used to filter which events to report.</span></span>  
  
## <a name="example"></a><span data-ttu-id="fe0aa-106">Esempio</span><span class="sxs-lookup"><span data-stu-id="fe0aa-106">Example</span></span>  
 [!code-cpp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/cpp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/cpp/form1.cpp#0)]
 [!code-csharp[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/CS/form1.cs#0)]
 [!code-vb[System.Windows.Forms.UserInputWalkthrough#0](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.UserInputWalkthrough/VB/form1.vb#0)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="fe0aa-107">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="fe0aa-107">Compiling the Code</span></span>  
 <span data-ttu-id="fe0aa-108">L'esempio presenta i requisiti seguenti:</span><span class="sxs-lookup"><span data-stu-id="fe0aa-108">This example requires:</span></span>  
  
- <span data-ttu-id="fe0aa-109">Riferimenti agli assembly System, System.Drawing e System.Windows.Forms.</span><span class="sxs-lookup"><span data-stu-id="fe0aa-109">References to the System, System.Drawing and System.Windows.Forms assemblies.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="fe0aa-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="fe0aa-110">See also</span></span>

- [<span data-ttu-id="fe0aa-111">Input dell'utente in Windows Forms</span><span class="sxs-lookup"><span data-stu-id="fe0aa-111">User Input in Windows Forms</span></span>](user-input-in-windows-forms.md)
