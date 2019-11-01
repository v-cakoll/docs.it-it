---
title: Utilizzo di controlli WPF
ms.date: 03/30/2017
helpviewer_keywords:
- Windows Forms Designer [Windows Forms], interoperability with WPF
- interoperability [WPF]
ms.assetid: 03c85dce-26ad-44cd-bc1d-8e0cb56de096
author: gewarren
ms.author: gewarren
manager: jillfra
ms.openlocfilehash: 5e05ec7fc503565333a4d05662a4e40d8d1193af
ms.sourcegitcommit: 5a28f8eb071fcc09b045b0c4ae4b96898673192e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/31/2019
ms.locfileid: "73197470"
---
# <a name="use-wpf-controls-in-windows-forms-apps"></a><span data-ttu-id="51fda-102">Usare i controlli WPF nelle app Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51fda-102">Use WPF controls in Windows Forms apps</span></span>

<span data-ttu-id="51fda-103">È possibile utilizzare i controlli Windows Presentation Foundation (WPF) nelle applicazioni basate su Windows Forms.</span><span class="sxs-lookup"><span data-stu-id="51fda-103">You can use Windows Presentation Foundation (WPF) controls in Windows Forms-based applications.</span></span> <span data-ttu-id="51fda-104">Sebbene si tratta di due tecnologie di visualizzazione diverse, interagiscono senza problemi.</span><span class="sxs-lookup"><span data-stu-id="51fda-104">Although these are two different view technologies, they interoperate smoothly.</span></span>

<span data-ttu-id="51fda-105">Il Progettazione Windows Form in Visual Studio fornisce un ambiente di progettazione visiva per l'hosting di controlli Windows Presentation Foundation.</span><span class="sxs-lookup"><span data-stu-id="51fda-105">The Windows Forms Designer in Visual Studio provides a visual design environment for hosting Windows Presentation Foundation controls.</span></span> <span data-ttu-id="51fda-106">Un controllo WPF è ospitato da un controllo Windows Forms speciale denominato <xref:System.Windows.Forms.Integration.ElementHost>.</span><span class="sxs-lookup"><span data-stu-id="51fda-106">A WPF control is hosted by a special Windows Forms control that's named <xref:System.Windows.Forms.Integration.ElementHost>.</span></span> <span data-ttu-id="51fda-107">Questo controllo consente al controllo WPF di partecipare al layout del form e di ricevere i messaggi della tastiera e del mouse.</span><span class="sxs-lookup"><span data-stu-id="51fda-107">This control enables the WPF control to participate in the form's layout and to receive keyboard and mouse messages.</span></span> <span data-ttu-id="51fda-108">In fase di progettazione è possibile disporre il controllo <xref:System.Windows.Forms.Integration.ElementHost> come qualsiasi Windows Forms controllo.</span><span class="sxs-lookup"><span data-stu-id="51fda-108">At design time, you can arrange the <xref:System.Windows.Forms.Integration.ElementHost> control just as you would any Windows Forms control.</span></span>

<span data-ttu-id="51fda-109">È inoltre possibile utilizzare Windows Forms controlli nelle applicazioni basate su WPF.</span><span class="sxs-lookup"><span data-stu-id="51fda-109">You can also use Windows Forms controls in WPF-based applications.</span></span> <span data-ttu-id="51fda-110">Per altre informazioni, vedere [progettazione di XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span><span class="sxs-lookup"><span data-stu-id="51fda-110">For more information, see [Design XAML in Visual Studio](/visualstudio/xaml-tools/designing-xaml-in-visual-studio).</span></span>

## <a name="see-also"></a><span data-ttu-id="51fda-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="51fda-111">See also</span></span>

- [<span data-ttu-id="51fda-112">Interoperatività di WPF e Windows Forms</span><span class="sxs-lookup"><span data-stu-id="51fda-112">WPF and Windows Forms interoperation</span></span>](../../wpf/advanced/wpf-and-windows-forms-interoperation.md)
