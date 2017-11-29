---
title: 'Procedura: Usare chiavi di caratteri del sistema'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-wpf
ms.tgt_pltfrm: 
ms.topic: article
helpviewer_keywords: resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 18781e3d71b9b30352323081e6d938350c6e53d1
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-use-system-fonts-keys"></a>Procedura: Usare chiavi di caratteri del sistema
Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema. <xref:System.Windows.SystemFonts>è una classe che contiene i valori del carattere di sistema e le risorse del carattere di sistema associati ai valori, ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Le metriche dei tipi di carattere del sistema possono essere usate come risorse statiche o dinamiche. Usare una risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.  
  
> [!NOTE]
>  Risorse dinamiche contenere la parola chiave *chiave* aggiunto al nome della proprietà.  
  
 L'esempio seguente illustra come accedere alle risorse dinamiche dei tipi di carattere del sistema e usarle per applicare uno stile a un pulsante o personalizzarlo. Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio viene creato un stile del pulsante che assegna <xref:System.Windows.SystemFonts> valori a un pulsante.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Vedere anche  
 [Disegnare un'area con un pennello di sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Utilizzare SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [Utilizzare la classe SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
