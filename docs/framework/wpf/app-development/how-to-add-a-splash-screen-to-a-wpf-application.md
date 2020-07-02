---
title: Come aggiungere una schermata iniziale
description: Informazioni su come aggiungere una finestra di avvio o una schermata iniziale a un'applicazione Windows Presentation Foundation (WPF).
ms.date: 08/18/2018
helpviewer_keywords:
- WPF [WPF], splash screen
- startup window [WPF]
- SplashScreen class [WPF]
- splash screen [WPF]
ms.assetid: d70a25c4-5fb9-4c27-b01d-b1b8ef39b3fd
ms.openlocfilehash: 0d0cf2e2a550320650c3b4a0c257071a0403c32b
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85617960"
---
# <a name="how-to-add-a-splash-screen-to-a-wpf-application"></a><span data-ttu-id="eb38a-103">Procedura: aggiungere una schermata iniziale in un'applicazione WPF</span><span class="sxs-lookup"><span data-stu-id="eb38a-103">How to: Add a Splash Screen to a WPF Application</span></span>

<span data-ttu-id="eb38a-104">In questo argomento viene illustrato come aggiungere una finestra di avvio o una *schermata iniziale*a un'applicazione Windows Presentation Foundation (WPF).</span><span class="sxs-lookup"><span data-stu-id="eb38a-104">This topic shows how to add a startup window, or *splash screen*, to a Windows Presentation Foundation (WPF) application.</span></span>

## <a name="to-add-an-existing-image-as-a-splash-screen"></a><span data-ttu-id="eb38a-105">Per aggiungere un'immagine esistente come schermata iniziale</span><span class="sxs-lookup"><span data-stu-id="eb38a-105">To add an existing image as a splash screen</span></span>

1. <span data-ttu-id="eb38a-106">Creare o trovare un'immagine che si vuole usare per la schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="eb38a-106">Create or find an image that you want to use for the splash screen.</span></span> <span data-ttu-id="eb38a-107">È possibile utilizzare qualsiasi formato di immagine supportato da Windows Imaging Component (WIC).</span><span class="sxs-lookup"><span data-stu-id="eb38a-107">You can use any image format that is supported by the Windows Imaging Component (WIC).</span></span> <span data-ttu-id="eb38a-108">Ad esempio, è possibile usare il formato BMP, GIF, JPEG, PNG o TIFF.</span><span class="sxs-lookup"><span data-stu-id="eb38a-108">For example, you can use the BMP, GIF, JPEG, PNG, or TIFF format.</span></span>

2. <span data-ttu-id="eb38a-109">Aggiungere il file di immagine al progetto di applicazione WPF.</span><span class="sxs-lookup"><span data-stu-id="eb38a-109">Add the image file to the WPF Application project.</span></span>

3. <span data-ttu-id="eb38a-110">In **Esplora soluzioni**selezionare l'immagine.</span><span class="sxs-lookup"><span data-stu-id="eb38a-110">In **Solution Explorer**, select the image.</span></span>

4. <span data-ttu-id="eb38a-111">Nella Finestra Proprietà fare clic sulla freccia a discesa relativa alla proprietà **azione di compilazione** .</span><span class="sxs-lookup"><span data-stu-id="eb38a-111">In the Properties window, click the drop-down arrow for the **Build Action** property.</span></span>

5. <span data-ttu-id="eb38a-112">Selezionare **SplashScreen** dall'elenco a discesa.</span><span class="sxs-lookup"><span data-stu-id="eb38a-112">Select **SplashScreen** from the drop-down list.</span></span>

6. <span data-ttu-id="eb38a-113">Premere **F5** per compilare ed eseguire l'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb38a-113">Press **F5** to build and run the application.</span></span>

     <span data-ttu-id="eb38a-114">L'immagine della schermata iniziale viene visualizzata al centro dello schermo, quindi si dissolve quando viene visualizzata la finestra principale dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="eb38a-114">The splash screen image appears in the center of the screen, and then fades when the main application window appears.</span></span>

## <a name="to-exclude-the-splash-screen-from-build"></a><span data-ttu-id="eb38a-115">Per escludere la schermata iniziale dalla compilazione</span><span class="sxs-lookup"><span data-stu-id="eb38a-115">To exclude the splash screen from build</span></span>

1. <span data-ttu-id="eb38a-116">In **Esplora soluzioni**selezionare l'immagine della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="eb38a-116">In **Solution Explorer**, select the splash screen image.</span></span>

2. <span data-ttu-id="eb38a-117">Nella finestra **Proprietà** impostare l'azione di **compilazione** su **nessuno**.</span><span class="sxs-lookup"><span data-stu-id="eb38a-117">In the **Properties** window, set the **Build Action** to **None**.</span></span>

## <a name="to-remove-the-splash-screen-from-an-application"></a><span data-ttu-id="eb38a-118">Per rimuovere la schermata iniziale da un'applicazione</span><span class="sxs-lookup"><span data-stu-id="eb38a-118">To remove the splash screen from an application</span></span>

<span data-ttu-id="eb38a-119">In **Esplora soluzioni**eliminare l'immagine della schermata iniziale.</span><span class="sxs-lookup"><span data-stu-id="eb38a-119">In **Solution Explorer**, delete the splash screen image.</span></span>

## <a name="see-also"></a><span data-ttu-id="eb38a-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="eb38a-120">See also</span></span>

- <xref:System.Windows.SplashScreen>
- <span data-ttu-id="eb38a-121">[Procedura: Aggiunta di elementi esistenti a un progetto](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span><span class="sxs-lookup"><span data-stu-id="eb38a-121">[How to: Add Existing Items to a Project](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2010/9f4t9t92(v=vs.100))</span></span>
