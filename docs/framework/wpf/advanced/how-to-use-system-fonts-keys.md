---
title: 'Procedura: Usare le chiavi dei tipi di carattere del sistema'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: e924f4c14d98380d9f4c0defe27d9f98c3293114
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59148928"
---
# <a name="how-to-use-system-fonts-keys"></a>Procedura: Usare le chiavi dei tipi di carattere del sistema
Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema. <xref:System.Windows.SystemFonts> è una classe che contiene i valori del tipo di carattere di sistema e le risorse del tipo di carattere di sistema associati ai valori, ad esempio, <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> e <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>.  
  
 Le metriche dei tipi di carattere del sistema possono essere usate come risorse statiche o dinamiche. Usare una risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.  
  
> [!NOTE]
>  Le risorse dinamiche hanno la parola chiave *chiave* accodato al nome della proprietà.  
  
 L'esempio seguente illustra come accedere alle risorse dinamiche dei tipi di carattere del sistema e usarle per applicare uno stile a un pulsante o personalizzarlo. Ciò [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] riportato di seguito viene creato uno stile pulsante che assegna <xref:System.Windows.SystemFonts> valori a un pulsante.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare un'area con un pennello di sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Utilizzare SystemParameters](how-to-use-systemparameters.md)
- [Utilizzare la classe SystemFonts](how-to-use-systemfonts.md)
