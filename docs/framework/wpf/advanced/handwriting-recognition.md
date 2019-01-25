---
title: Riconoscimento della grafia
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
ms.openlocfilehash: 8f520b80970bfeebdfea01a6c722634efd99ffe7
ms.sourcegitcommit: 6b308cf6d627d78ee36dbbae8972a310ac7fd6c8
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/23/2019
ms.locfileid: "54725389"
---
# <a name="handwriting-recognition"></a><span data-ttu-id="92189-102">Riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="92189-102">Handwriting Recognition</span></span>
<span data-ttu-id="92189-103">Questa sezione illustra alcune nozioni di base del riconoscimento relativamente all'input penna digitale nella piattaforma WPF.</span><span class="sxs-lookup"><span data-stu-id="92189-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="92189-104">Soluzioni di riconoscimento</span><span class="sxs-lookup"><span data-stu-id="92189-104">Recognition Solutions</span></span>  
 <span data-ttu-id="92189-105">Nell'esempio seguente viene mostrato come riconoscere l'input penna usando la classe [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx).</span><span class="sxs-lookup"><span data-stu-id="92189-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="92189-106">Per questo esempio è necessario che il riconoscimento grafia sia installato nel sistema.</span><span class="sxs-lookup"><span data-stu-id="92189-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="92189-107">Creare un nuovo progetto di applicazione WPF in Visual Studio denominato **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="92189-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="92189-108">Sostituire il contenuto del file Window1.xaml con il codice XAML seguente.</span><span class="sxs-lookup"><span data-stu-id="92189-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="92189-109">Questo codice esegue il rendering dell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="92189-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="92189-110">Aggiungere un riferimento all'assembly Microsoft Ink Microsoft.Ink.dll, che può trovarsi in \Programmi\File comuni\Microsoft Shared\Ink.</span><span class="sxs-lookup"><span data-stu-id="92189-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="92189-111">Sostituire il contenuto del file code-behind con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="92189-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="92189-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="92189-112">See also</span></span>
- <span data-ttu-id="92189-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span><span class="sxs-lookup"><span data-stu-id="92189-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span></span>
