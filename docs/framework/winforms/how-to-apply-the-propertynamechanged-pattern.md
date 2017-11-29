---
title: 'Procedura: applicare il modello PropertyNameChanged'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- custom controls [Windows Forms], property changes (using code)
- data binding [Windows Forms], custom controls
- PropertyNameChanged pattern [Windows Forms], applying
ms.assetid: aa47ddf6-5223-40c4-833f-a78992194836
caps.latest.revision: "5"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 4f53dd2fdaa622e022f49c153b6dbc83030ae791
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-apply-the-propertynamechanged-pattern"></a><span data-ttu-id="51751-102">Procedura: applicare il modello PropertyNameChanged</span><span class="sxs-lookup"><span data-stu-id="51751-102">How to: Apply the PropertyNameChanged Pattern</span></span>
<span data-ttu-id="51751-103">Esempio di codice seguente viene illustrato come applicare il *PropertyName*modello Changed a un controllo personalizzato.</span><span class="sxs-lookup"><span data-stu-id="51751-103">The following code example demonstrates how to apply the *PropertyName*Changed pattern to a custom control.</span></span> <span data-ttu-id="51751-104">Applicare questo modello quando si implementano controlli personalizzati che vengono utilizzati con il motore di associazione di dati di Windows Form.</span><span class="sxs-lookup"><span data-stu-id="51751-104">Apply this pattern when you implement custom controls that are used with the Windows Forms data binding engine.</span></span>  
  
## <a name="example"></a><span data-ttu-id="51751-105">Esempio</span><span class="sxs-lookup"><span data-stu-id="51751-105">Example</span></span>  
 [!code-csharp[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/csharp/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/CS/Form1.cs#3)]
 [!code-vb[System.Windows.Forms.ChangeNotification#3](../../../samples/snippets/visualbasic/VS_Snippets_Winforms/System.Windows.Forms.ChangeNotification/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a><span data-ttu-id="51751-106">Compilazione del codice</span><span class="sxs-lookup"><span data-stu-id="51751-106">Compiling the Code</span></span>  
 <span data-ttu-id="51751-107">Per compilare l'esempio di codice precedente:</span><span class="sxs-lookup"><span data-stu-id="51751-107">To compile the previous code example:</span></span>  
  
-   <span data-ttu-id="51751-108">Incollare il codice in un file di codice vuoto.</span><span class="sxs-lookup"><span data-stu-id="51751-108">Paste the code into an empty code file.</span></span> <span data-ttu-id="51751-109">È necessario utilizzare il controllo personalizzato in un Windows Form che contiene un `Main` metodo.</span><span class="sxs-lookup"><span data-stu-id="51751-109">You must use the custom control on a Windows Form that contains a `Main` method.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="51751-110">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51751-110">See Also</span></span>  
 [<span data-ttu-id="51751-111">Procedura: Implementare l'interfaccia INotifyPropertyChanged</span><span class="sxs-lookup"><span data-stu-id="51751-111">How to: Implement the INotifyPropertyChanged Interface</span></span>](../../../docs/framework/winforms/how-to-implement-the-inotifypropertychanged-interface.md)  
 [<span data-ttu-id="51751-112">Notifica delle modifiche nel data binding dei Windows Form</span><span class="sxs-lookup"><span data-stu-id="51751-112">Change Notification in Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/change-notification-in-windows-forms-data-binding.md)  
 [<span data-ttu-id="51751-113">Data binding in Windows Form</span><span class="sxs-lookup"><span data-stu-id="51751-113">Windows Forms Data Binding</span></span>](../../../docs/framework/winforms/windows-forms-data-binding.md)
