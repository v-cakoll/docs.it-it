---
title: 'Procedura: Usare le chiavi dei parametri di sistema'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemParameters class
- classes [WPF], SystemParameters
ms.assetid: 77571283-d16c-45bb-9f69-cafbbf72b21e
ms.openlocfilehash: edacb4b98ab01f081f668dc3374f6588492210d9
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918376"
---
# <a name="how-to-use-system-parameters-keys"></a>Procedura: Usare le chiavi dei parametri di sistema
Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema. <xref:System.Windows.SystemParameters>è una classe che contiene sia i valori dei parametri di sistema che le chiavi di risorsa associate ai valori, <xref:System.Windows.SystemParameters.FullPrimaryScreenHeight%2A> ad <xref:System.Windows.SystemParameters.FullPrimaryScreenHeightKey%2A>esempio e. Le metriche dei parametri di sistema possono essere usate come risorse statiche o dinamiche. Usare una risorsa dinamica per aggiornare automaticamente le metriche dei parametri durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.  
  
> [!NOTE]
> Per le risorse dinamiche è stata aggiunta la parola *chiave Key* al nome della proprietà.  
  
 L'esempio seguente illustra come accedere alle risorse dinamiche dei parametri di sistema e usarle per applicare uno stile a un pulsante o personalizzarlo. Questo [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] esempio consente di ridimensionare un pulsante <xref:System.Windows.SystemParameters> assegnando valori alla larghezza e all'altezza del pulsante.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SystemRes_snip#ParameterDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#parameterdynamicresources)]  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare un'area con un pennello di sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Utilizzare la classe SystemFonts](how-to-use-systemfonts.md)
- [Utilizzare SystemParameters](how-to-use-systemparameters.md)
