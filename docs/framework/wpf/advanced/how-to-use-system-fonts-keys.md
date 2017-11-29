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
# <a name="how-to-use-system-fonts-keys"></a><span data-ttu-id="13480-102">Procedura: Usare chiavi di caratteri del sistema</span><span class="sxs-lookup"><span data-stu-id="13480-102">How to: Use System Fonts Keys</span></span>
<span data-ttu-id="13480-103">Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema.</span><span class="sxs-lookup"><span data-stu-id="13480-103">System resources expose a number of system metrics as resources to help developers create visuals that are consistent with system settings.</span></span> <span data-ttu-id="13480-104"><xref:System.Windows.SystemFonts>è una classe che contiene i valori del carattere di sistema e le risorse del carattere di sistema associati ai valori, ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span><span class="sxs-lookup"><span data-stu-id="13480-104"><xref:System.Windows.SystemFonts> is a class that contains both system font values and system font resources that bind to the values—for example, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> and <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.</span></span>  
  
 <span data-ttu-id="13480-105">Le metriche dei tipi di carattere del sistema possono essere usate come risorse statiche o dinamiche.</span><span class="sxs-lookup"><span data-stu-id="13480-105">System font metrics can be used as either static or dynamic resources.</span></span> <span data-ttu-id="13480-106">Usare una risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.</span><span class="sxs-lookup"><span data-stu-id="13480-106">Use a dynamic resource if you want the font metric to update automatically while the application runs; otherwise use a static resource.</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="13480-107">Risorse dinamiche contenere la parola chiave *chiave* aggiunto al nome della proprietà.</span><span class="sxs-lookup"><span data-stu-id="13480-107">Dynamic resources have the keyword *Key* appended to the property name.</span></span>  
  
 <span data-ttu-id="13480-108">L'esempio seguente illustra come accedere alle risorse dinamiche dei tipi di carattere del sistema e usarle per applicare uno stile a un pulsante o personalizzarlo.</span><span class="sxs-lookup"><span data-stu-id="13480-108">The following example shows how to access and use system font dynamic resources to style or customize a button.</span></span> <span data-ttu-id="13480-109">Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio viene creato un stile del pulsante che assegna <xref:System.Windows.SystemFonts> valori a un pulsante.</span><span class="sxs-lookup"><span data-stu-id="13480-109">This [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] example creates a button style that assigns <xref:System.Windows.SystemFonts> values to a button.</span></span>  
  
## <a name="example"></a><span data-ttu-id="13480-110">Esempio</span><span class="sxs-lookup"><span data-stu-id="13480-110">Example</span></span>  
 [!code-xaml[SystemRes_snip#FontDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a><span data-ttu-id="13480-111">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="13480-111">See Also</span></span>  
 [<span data-ttu-id="13480-112">Disegnare un'area con un pennello di sistema</span><span class="sxs-lookup"><span data-stu-id="13480-112">Paint an Area with a System Brush</span></span>](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [<span data-ttu-id="13480-113">Utilizzare SystemParameters</span><span class="sxs-lookup"><span data-stu-id="13480-113">Use SystemParameters</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)  
 [<span data-ttu-id="13480-114">Utilizzare la classe SystemFonts</span><span class="sxs-lookup"><span data-stu-id="13480-114">Use SystemFonts</span></span>](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)
