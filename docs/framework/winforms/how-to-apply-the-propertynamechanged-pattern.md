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
ms.openlocfilehash: 01afa713e97206ea192ba55dc2affad20163f872
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64665267"
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="22546-102">Procedura: Applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="22546-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="22546-103">Esempio di codice seguente viene illustrato come applicare la *PropertyName*Changed pattern a un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="22546-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="22546-104">Applicare questo modello quando si implementano controlli personalizzati che vengono usati con il motore di data binding di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="22546-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="22546-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="22546-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="22546-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="22546-106">Compiling the Code</span></span>  
 <span data-ttu-id="22546-107">Per compilare l'esempio di codice precedente:</span><span class="sxs-lookup"><span data-stu-id="22546-107">To compile the previous code example:</span></span>  
  
- <span data-ttu-id="22546-108">Incollare il codice in un file di codice vuoto.</span><span class="sxs-lookup"><span data-stu-id="22546-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="22546-109">È necessario usare il controllo personalizzato in un Form Windows che contiene un `Main` (metodo).</span><span class="sxs-lookup"><span data-stu-id="22546-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="22546-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="22546-110">See also</span></span>

- [<span data-ttu-id="22546-111">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="22546-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](how-to-implement-the-inotifypropertychanged-interface.md)
- [<span data-ttu-id="22546-112">Notifica delle modifiche nel data binding dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="22546-112">Change Notification in Windows Forms Data Binding</span></span>](change-notification-in-windows-forms-data-binding.md)
- [<span data-ttu-id="22546-113">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="22546-113">Windows Forms Data Binding</span></span>](windows-forms-data-binding.md)
