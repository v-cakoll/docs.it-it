---
title: "Procedura: Rendere persistenti e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- application-scope properties [WPF], persisting
- persisting application-scope properties [WPF]
- properties [WPF], persisting
- restoring application-scope properties [WPF]
- properties [WPF], restoring
- application-scope properties [WPF], restoring
ms.assetid: 55d5904a-f444-4eb5-abd3-6bc74dd14226
ms.openlocfilehash: 99b04060d4e7c14313655010dc4fbd5ce1c90487
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59134953"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a><span data-ttu-id="507a8-102">Procedura: Rendere persistenti e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione</span><span class="sxs-lookup"><span data-stu-id="507a8-102">How to: Persist and Restore Application-Scope Properties Across Application Sessions</span></span>
<span data-ttu-id="507a8-103">In questo esempio viene illustrato come rendere persistenti le proprietà dell'ambito dell'applicazione quando un'applicazione viene arrestata e come ripristinare le proprietà dell'ambito dell'applicazione quando un'applicazione è successiva avvio.</span><span class="sxs-lookup"><span data-stu-id="507a8-103">This example shows how to persist application-scope properties when an application shuts down, and how to restore application-scope properties when an application is next launch.</span></span>  
  
## <a name="example"></a><span data-ttu-id="507a8-104">Esempio</span><span class="sxs-lookup"><span data-stu-id="507a8-104">Example</span></span>  
 <span data-ttu-id="507a8-105">Rende persistenti le proprietà dell'ambito dell'applicazione per l'applicazione e li Ripristina da un archivio isolato.</span><span class="sxs-lookup"><span data-stu-id="507a8-105">The application persists application-scope properties to, and restores them from, isolated storage.</span></span> <span data-ttu-id="507a8-106">Spazio di memorizzazione isolato è un'area di archiviazione protetta che può essere utilizzata in modo sicuro per le applicazioni senza autorizzazione di accesso di file.</span><span class="sxs-lookup"><span data-stu-id="507a8-106">Isolated storage is a protected storage area that can safely be used by applications without file access permission.</span></span>  <span data-ttu-id="507a8-107">Il *app. XAML* file definisce il `App_Startup` metodo come gestore per il <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e il `App_Exit` metodo come gestore per il <xref:System.Windows.Application.Exit?displayProperty=nameWithType> evento, come illustrato nelle righe evidenziate del primo esempio.</span><span class="sxs-lookup"><span data-stu-id="507a8-107">The *App.xaml* file defines the `App_Startup` method as the handler for the <xref:System.Windows.Application.Startup?displayProperty=nameWithType> event, and the `App_Exit` method as the handler for the  <xref:System.Windows.Application.Exit?displayProperty=nameWithType> event, as shown in the highlighted lines of the first example.</span></span> <span data-ttu-id="507a8-108">Nel secondo esempio viene illustrata una parte del *App.xaml.cs* e *app* i file che evidenzia il codice per il `App_Startup` (metodo), che consente di ripristinare le proprietà dell'ambito dell'applicazione e la `App_Exit` metodo, che consente di salvare le proprietà dell'ambito dell'applicazione.</span><span class="sxs-lookup"><span data-stu-id="507a8-108">The second example shows a portion of the *App.xaml.cs* and *App.xaml.vb* files that highlights the code for the `App_Startup` method, which restores application-scope properties, and the `App_Exit` method, which saves application-scope properties.</span></span>

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
