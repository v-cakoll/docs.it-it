---
title: 'Procedura: Aprire una finestra'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- windows [WPF], opening
- opening windows [WPF]
ms.assetid: 6b91b2bb-fda7-491d-a72e-139dd630a5b0
ms.openlocfilehash: 9ce7ffb3f46dd869fda7893745b531bd02d18ee1
ms.sourcegitcommit: 0c48191d6d641ce88d7510e319cf38c0e35697d0
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/05/2019
ms.locfileid: "57373569"
---
# <a name="how-to-open-a-window"></a><span data-ttu-id="d4935-102">Procedura: Aprire una finestra</span><span class="sxs-lookup"><span data-stu-id="d4935-102">How to: Open a Window</span></span>
<span data-ttu-id="d4935-103">In questo esempio viene illustrato come aprire una finestra.</span><span class="sxs-lookup"><span data-stu-id="d4935-103">This example shows how to open a window.</span></span>  
  
## <a name="example"></a><span data-ttu-id="d4935-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="d4935-104">Example</span></span>  
 <span data-ttu-id="d4935-105">Viene aperta una finestra creando <xref:System.Windows.Window> e chiamando il <xref:System.Windows.Window.Show%2A> (metodo).</span><span class="sxs-lookup"><span data-stu-id="d4935-105">A window is opened by instantiating <xref:System.Windows.Window> and calling the <xref:System.Windows.Window.Show%2A> method.</span></span> <span data-ttu-id="d4935-106"><xref:System.Windows.Window.Show%2A> Apre una finestra e viene restituito immediatamente senza attendere che la nuova finestra da chiudere.</span><span class="sxs-lookup"><span data-stu-id="d4935-106"><xref:System.Windows.Window.Show%2A> opens a window and returns immediately without waiting for the new window to close.</span></span> <span data-ttu-id="d4935-107">Questo tipo di finestra è noto anche come un *modale* finestra e non limita l'input dell'utente.</span><span class="sxs-lookup"><span data-stu-id="d4935-107">This type of window is also known as a *modeless* window, and doesn't restrict user input.</span></span>  
  
 [!code-csharp[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/CSharp/MainWindow.xaml.cs#opennewwindowcode)]
 [!code-vb[HOWTOWindowManagementSnippets#OpenNewWindowCODE](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOWindowManagementSnippets/visualbasic/mainwindow.xaml.vb#opennewwindowcode)]  
  
## <a name="net-framework-security"></a><span data-ttu-id="d4935-108">Sicurezza di .NET Framework</span><span class="sxs-lookup"><span data-stu-id="d4935-108">.NET Framework Security</span></span>  
 <span data-ttu-id="d4935-109">Creazione di un'istanza <xref:System.Windows.Window> richiede l'autorizzazione per chiamare i metodi nativi non sicuri (vedere <xref:System.Windows.Window.%23ctor%2A>).</span><span class="sxs-lookup"><span data-stu-id="d4935-109">Instantiating <xref:System.Windows.Window> requires permission to call unsafe native methods (see <xref:System.Windows.Window.%23ctor%2A>).</span></span>
