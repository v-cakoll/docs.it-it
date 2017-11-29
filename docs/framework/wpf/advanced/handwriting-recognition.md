---
title: Riconoscimento della grafia
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- handwriting recognition [WPF]
- recognition of handwriting [WPF]
ms.assetid: f4e8576d-e731-4bac-9818-22e2ae636636
caps.latest.revision: "11"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: f8a202d4698c968a91a3d930138290cedfe3a83b
ms.sourcegitcommit: c2e216692ef7576a213ae16af2377cd98d1a67fa
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/22/2017
---
# <a name="handwriting-recognition"></a><span data-ttu-id="f90bf-102">Riconoscimento della grafia</span><span class="sxs-lookup"><span data-stu-id="f90bf-102">Handwriting Recognition</span></span>
<span data-ttu-id="f90bf-103">Questa sezione illustra alcune nozioni di base del riconoscimento relativamente all'input penna digitale nella piattaforma WPF.</span><span class="sxs-lookup"><span data-stu-id="f90bf-103">This section discusses the fundamentals of recognition as it pertains to digital ink in the WPF platform.</span></span>  
  
## <a name="recognition-solutions"></a><span data-ttu-id="f90bf-104">Soluzioni di riconoscimento</span><span class="sxs-lookup"><span data-stu-id="f90bf-104">Recognition Solutions</span></span>  
 <span data-ttu-id="f90bf-105">Nell'esempio seguente viene mostrato come riconoscere l'input penna usando la classe [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx).</span><span class="sxs-lookup"><span data-stu-id="f90bf-105">The following example shows how to recognize ink using the [Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx) class.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="f90bf-106">Per questo esempio è necessario che il riconoscimento grafia sia installato nel sistema.</span><span class="sxs-lookup"><span data-stu-id="f90bf-106">This sample requires that handwriting recognizers be installed on the system.</span></span>  
  
 <span data-ttu-id="f90bf-107">Creare un nuovo progetto di applicazione WPF in Visual Studio denominato **InkRecognition**.</span><span class="sxs-lookup"><span data-stu-id="f90bf-107">Create a new WPF application project in Visual Studio called **InkRecognition**.</span></span> <span data-ttu-id="f90bf-108">Sostituire il contenuto del file Window1.xaml con il codice XAML seguente.</span><span class="sxs-lookup"><span data-stu-id="f90bf-108">Replace the contents of the Window1.xaml file with the following XAML code.</span></span> <span data-ttu-id="f90bf-109">Questo codice esegue il rendering dell'interfaccia utente dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="f90bf-109">This code renders the application's user interface.</span></span>  
  
 [!code-xaml[InkRecognition#1](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml#1)]  
  
 <span data-ttu-id="f90bf-110">Aggiungere un riferimento all'assembly Microsoft Ink Microsoft.Ink.dll, che può trovarsi in \Programmi\File comuni\Microsoft Shared\Ink.</span><span class="sxs-lookup"><span data-stu-id="f90bf-110">Add a reference to the Microsoft Ink assembly, Microsoft.Ink.dll, which can be found in \Program Files\Common Files\Microsoft Shared\Ink.</span></span> <span data-ttu-id="f90bf-111">Sostituire il contenuto del file code-behind con il codice seguente.</span><span class="sxs-lookup"><span data-stu-id="f90bf-111">Replace the contents of the code behind file with the following code.</span></span>  
  
 [!code-csharp[InkRecognition#2](../../../../samples/snippets/csharp/VS_Snippets_Wpf/InkRecognition/CSharp/Window1.xaml.cs#2)]
 [!code-vb[InkRecognition#2](../../../../samples/snippets/visualbasic/VS_Snippets_Wpf/InkRecognition/VisualBasic/Window1.xaml.vb#2)]  
  
## <a name="see-also"></a><span data-ttu-id="f90bf-112">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="f90bf-112">See Also</span></span>  
 <span data-ttu-id="f90bf-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span><span class="sxs-lookup"><span data-stu-id="f90bf-113">[Microsoft.Ink.InkCollector](https://msdn.microsoft.com/library/microsoft.ink.inkcollector\(v=vs.90\).aspx)</span></span>
