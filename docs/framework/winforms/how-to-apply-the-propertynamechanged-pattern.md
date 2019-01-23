---
title: 'Procedura: Applicare il modello PropertyNameChanged'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
ms.openlocfilehash: 82856405ab3c9581b398f358e5bf9ecf989ce193
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54539766"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="f5433-102">Procedura: Applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="f5433-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="f5433-103">Esempio di codice seguente viene illustrato come applicare la *PropertyName*Changed pattern a un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="f5433-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="f5433-104">Applicare questo modello quando si implementano controlli personalizzati che vengono usati con il motore di data binding di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="f5433-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="f5433-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="f5433-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="f5433-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="f5433-106">Compiling the Code</span></span>  
 <span data-ttu-id="f5433-107">Per compilare l'esempio di codice precedente:</span><span class="sxs-lookup"><span data-stu-id="f5433-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="f5433-108">Incollare il codice in un file di codice vuoto.</span><span class="sxs-lookup"><span data-stu-id="f5433-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="f5433-109">È necessario usare il controllo personalizzato in un Form Windows che contiene un `Main` (metodo).</span><span class="sxs-lookup"><span data-stu-id="f5433-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="f5433-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f5433-110">See also</span></span>
- [<span data-ttu-id="f5433-111">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="f5433-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="f5433-112">Notifica delle modifiche nel data binding dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="f5433-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="f5433-113">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="f5433-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
