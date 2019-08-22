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
ms.openlocfilehash: d9c2dda2745e7528902b6b1c4f46d17264d1a8d8
ms.sourcegitcommit: cdf67135a98a5a51913dacddb58e004a3c867802
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/21/2019
ms.locfileid: "69666718"
---
# <a name="how-to-persist-and-restore-application-scope-properties-across-application-sessions"></a>Procedura: Rendere persistenti e ripristinare le proprietà dell'ambito dell'applicazione nelle sessioni dell'applicazione
Questo esempio illustra come salvare in modo permanente le proprietà dell'ambito dell'applicazione quando un'applicazione viene arrestata e come ripristinare le proprietà dell'ambito dell'applicazione al successivo avvio di un'applicazione.  
  
## <a name="example"></a>Esempio  
 L'applicazione salva in modo permanente le proprietà dell'ambito dell'applicazione e le ripristina dallo spazio di memorizzazione isolato. Lo spazio di memorizzazione isolato è un'area di archiviazione protetta che può essere usata in modo sicuro dalle applicazioni senza autorizzazione di accesso ai file.  Il file *app. XAML* definisce il `App_Startup` metodo come gestore per l' <xref:System.Windows.Application.Startup?displayProperty=nameWithType> evento e il `App_Exit` metodo come gestore per l' <xref:System.Windows.Application.Exit?displayProperty=nameWithType> evento, come illustrato nelle righe evidenziate del primo esempio. Nel secondo esempio viene illustrata una parte dei file *app.XAML.cs* e *app. XAML. vb* che evidenzia il codice per `App_Startup` il metodo, che consente di ripristinare le proprietà dell'ambito dell'applicazione `App_Exit` e il metodo, che salva l'ambito dell'applicazione. Proprietà.

 [!code-xaml[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesXAML1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml?highlight=1-7)]
  
 [!code-csharp[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/csharp/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/CSharp/App.xaml.cs?highlight=17-55)]
 [!code-vb[HOWTOApplicationModelSnippets#PersistRestoreAppScopePropertiesCODEBEHIND1](~/samples/snippets/visualbasic/VS_Snippets_Wpf/HOWTOApplicationModelSnippets/visualbasic/application.xaml.vb?highlight=14-45)]
