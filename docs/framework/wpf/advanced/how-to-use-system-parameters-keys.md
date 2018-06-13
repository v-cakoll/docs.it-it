---
title: 'Procedura: Usare chiavi dei parametri di sistema'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: c94719c8268cbbdadbe6805d531540e1f34ee5d1
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33544716"
---
# <a name="how-to-use-system-parameters-keys"></a>Procedura: Usare chiavi dei parametri di sistema
Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema. <xref:System.Windows.SystemParameters> è una classe che contiene i valori dei parametri di sistema e le chiavi di risorsa che l'associazione ai valori, ad esempio <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> e <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>. Le metriche dei parametri di sistema possono essere usate come risorse statiche o dinamiche. Usare una risorsa dinamica per aggiornare automaticamente le metriche dei parametri durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.  
  
> [!NOTE]
>  Risorse dinamiche contenere la parola chiave *chiave* aggiunto al nome della proprietà.  
  
 L'esempio seguente illustra come accedere alle risorse dinamiche dei parametri di sistema e usarle per applicare uno stile a un pulsante o personalizzarlo. Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] viene ridimensionato un pulsante assegnando <xref:System.Windows.SystemParameters> valori di larghezza e altezza del pulsante.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](../../../../samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Vedere anche  
 [Disegnare un'area con un pennello di sistema](../../../../docs/framework/wpf/graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)  
 [Utilizzare la classe SystemFonts](../../../../docs/framework/wpf/advanced/how-to-use-systemfonts.md)  
 [Utilizzare SystemParameters](../../../../docs/framework/wpf/advanced/how-to-use-systemparameters.md)
