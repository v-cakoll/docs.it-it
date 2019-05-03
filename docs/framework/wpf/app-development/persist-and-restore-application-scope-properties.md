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
ms.sourcegitcommit: 9b552addadfb57fab0b9e7852ed4f1f1b8a42f8e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/23/2019
ms.locfileid: "61788674"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a>Procedura: Rendere persistenti e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione
In questo esempio viene illustrato come rendere persistenti le proprietà dell'ambito dell'applicazione quando un'applicazione viene arrestata e come ripristinare le proprietà dell'ambito dell'applicazione quando un'applicazione è successiva avvio.  
  
## <a name="example"></a>Esempio  
 Rende persistenti le proprietà dell'ambito dell'applicazione per l'applicazione e li Ripristina da un archivio isolato. Spazio di memorizzazione isolato è un'area di archiviazione protetta che può essere utilizzata in modo sicuro per le applicazioni senza autorizzazione di accesso di file.  Il *app. XAML* file definisce il `App_Startup` metodo come gestore per il <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e il `App_Exit` metodo come gestore per il <xref:System.Windows.Application.Exit?displayProperty=nameWithType> evento, come illustrato nelle righe evidenziate del primo esempio. Nel secondo esempio viene illustrata una parte del *App.xaml.cs* e *app* i file che evidenzia il codice per il `App_Startup` (metodo), che consente di ripristinare le proprietà dell'ambito dell'applicazione e la `App_Exit` metodo, che consente di salvare le proprietà dell'ambito dell'applicazione.

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb#persistrestoreappscopepropertiescodebehind1)]
