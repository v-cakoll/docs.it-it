---
title: Sviluppo per piattaforme multiple con .NET Framework
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-standard
ms.tgt_pltfrm: 
ms.topic: article
ms.assetid: b153baaa-130c-4169-860b-e580591de91e
caps.latest.revision: "13"
author: mairaw
ms.author: mairaw
manager: wpickett
ms.openlocfilehash: 6ad765ca133b9757d7649f55b9dc100084a753e0
ms.sourcegitcommit: bd1ef61f4bb794b25383d3d72e71041a5ced172e
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/18/2017
---
# <a name="developing-for-multiple-platforms-with-the-net-framework"></a>Sviluppo per piattaforme multiple con .NET Framework
Con .NET Framework e Visual Studio è possibile sviluppare app per piattaforme Microsoft e non Microsoft.  
  
## <a name="options-for-cross-platform-development"></a>Opzioni per lo sviluppo multipiattaforma  
 Per sviluppare applicazioni per più piattaforme è possibile condividere il codice sorgente ed effettuare chiamate tra il codice .NET Framework e le API di Windows Runtime.  
  
|Per...|Usare...|  
|-----------------------|------------|  
|Condividere codice sorgente tra app Windows Phone 8.1 e app Windows 8.1|**Progetti condivisi** (modello di App universali in Visual Studio 2013 Update 2).<br /><br /> -Attualmente nessun supporto di Visual Basic.<br />-È possibile separare il codice specifico della piattaforma utilizzando #`if` istruzioni.<br /><br /> Per informazioni dettagliate, vedere:<br /><br /> -   [Compilare le app destinate a Windows e Windows Phone usando Visual Studio](http://msdn.microsoft.com/library/windows/apps/dn609832.aspx) (articolo MSDN)<br />-   [Utilizzo di Visual Studio per creare App XAML universali](http://blogs.msdn.com/b/visualstudio/archive/2014/04/14/using-visual-studio-to-build-universal-xaml-apps.aspx) (post di blog)<br />-   [Utilizzando Visual Studio per compilare App XAML convergenti](http://channel9.msdn.com/Events/Build/2014/3-591) (video)|  
|Condividere i binari tra app destinate a piattaforme diverse|**Progetti libreria di classi portabile** per il codice è indipendente dalla piattaforma.<br /><br /> -Questo approccio viene in genere utilizzato per il codice che implementa la logica di business.<br />-È possibile utilizzare Visual Basic o c#.<br />-Supporto API varia a seconda della piattaforma.<br />-I progetti libreria di classi portabili destinate a Windows 8.1 e Windows Phone 8.1 supportano APIs di Windows Runtime e XAML. Queste funzionalità non sono disponibili nelle versioni precedenti di Libreria di classi portabile.<br />-Se necessario, è possibile astrarre il codice specifico della piattaforma usando interfacce o classi astratte.<br /><br /> Per informazioni dettagliate, vedere:<br /><br /> -   [Libreria di classi portabile](../../../docs/standard/cross-platform/cross-platform-development-with-the-portable-class-library.md) (articolo MSDN)<br />-   [Come rendere portabile classe le librerie per l'utente](http://blogs.msdn.com/b/dsplaisted/archive/2012/08/27/how-to-make-portable-class-libraries-work-for-you.aspx) (post di blog)<br />-   [Utilizzo di libreria di classi portabile con MVVM](../../../docs/standard/cross-platform/using-portable-class-library-with-model-view-view-model.md) (articolo MSDN)<br />-   [Risorse App per librerie destinate a più piattaforme](../../../docs/standard/cross-platform/app-resources-for-libraries-that-target-multiple-platforms.md) (articolo MSDN)<br />-   [.NET portability Analyzer](http://visualstudiogallery.msdn.microsoft.com/1177943e-cfb7-4822-a8a6-e56c7905292b) (estensione di Visual Studio)|  
|Condividere codice sorgente tra app per piattaforme diverse da Windows 8.1 e Windows Phone 8.1|**Aggiungi come collegamento** funzionalità.<br /><br /> -Questo approccio è idoneo per la logica che è comune a entrambe le app, ma non è portabile, per qualche motivo. È possibile usare questa funzionalità per il codice C# o Visual Basic.<br />     Ad esempio, Windows Phone 8 e Windows 8 condividono le API di Windows Runtime, ma le librerie di classi portabili non supportano Windows Runtime per queste piattaforme. È possibile usare `Add as link` per condividere il codice Windows Runtime tra un'app Windows Phone 8 e un'app di Windows Store destinata a Windows 8.<br /><br /> Per informazioni dettagliate, vedere:<br /><br /> -   [Condividere codice con Aggiungi come collegamento](http://msdn.microsoft.com/library/windowsphone/develop/jj714082\(v=vs.105\).aspx) (articolo MSDN)<br />-   [Procedura: aggiungere elementi esistenti a un progetto](http://msdn.microsoft.com/library/vstudio/9f4t9t92\(v=vs.100\).aspx) (articolo MSDN)|  
|Scrivere app di Windows Store usando .NET Framework o chiamare API di Windows Runtime API dal codice .NET Framework|**Windows Runtime APIs** dal codice .NET Framework c# o Visual Basic e utilizzare .NET Framework per creare applicazioni Windows Store. È opportuno tenere presenti le differenze relative alle API tra le due piattaforme, tuttavia sono disponibili classi che agevolano la gestione di queste differenze.<br /><br /> Per informazioni dettagliate, vedere:<br /><br /> -   [.NET framework il supporto per applicazioni Windows Store e Windows Runtime](../../../docs/standard/cross-platform/support-for-windows-store-apps-and-windows-runtime.md) (articolo MSDN)<br />-   [Passaggio di un URI a Windows Runtime](../../../docs/standard/cross-platform/passing-a-uri-to-the-windows-runtime.md) (articolo MSDN)<br />-   <!--zz <xref:System.IO.WindowsRuntimeStreamExtensions>-->`System.IO.WindowsRuntimeStreamExtensions` (Pagina di riferimento API su MSDN)<br />-   <!--zz <xref:System.WindowsRuntimeSystemExtensions>-->`System.WindowsRuntimeSystemExtensions` (Pagina di riferimento API su MSDN)|  
|Sviluppare app .NET Framework per piattaforme non Microsoft|**Assembly di riferimento di libreria di classi portabile** in .NET Framework e uno strumento di terze parti o estensione di Visual Studio, ad esempio Xamarin.<br /><br /> Per informazioni dettagliate, vedere:<br /><br /> -   [Libreria di classi portabile su tutte le piattaforme.](http://blogs.msdn.com/b/dotnet/archive/2013/10/14/portable-class-library-pcl-now-available-on-all-platforms.aspx) (post di blog)<br />-   [Xamarin](http://xamarin.com/visual-studio) (sito Web Xamarin)|  
|Usare JavaScript e HTML per lo sviluppo multipiattaforma|**Modelli per applicazioni universali** in Visual Studio 2013 Update 2 per lo sviluppo utilizzando APIs di Windows Runtime per Windows 8.1 e Windows Phone 8.1. Attualmente non è possibile usare JavaScript e HTML con le API .NET Framework per sviluppare app multipiattaforma.<br /><br /> Per informazioni dettagliate, vedere:<br /><br /> -   [Modelli di progetto di JavaScript](http://msdn.microsoft.com/library/windows/apps/hh758331.aspx)<br />-   [Porting di un'applicazione di Windows Runtime scritte in JavaScript per Windows Phone](http://msdn.microsoft.com/library/windows/apps/dn636144.aspx)|
