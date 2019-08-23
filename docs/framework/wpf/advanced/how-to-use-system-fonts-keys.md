---
title: 'Procedura: Usare le chiavi dei tipi di carattere del sistema'
ms.date: 03/30/2017
helpviewer_keywords:
- resource keys [WPF], SystemFonts class
ms.assetid: 036ebea7-5677-4f60-8ba4-56c9f9d9b8bd
ms.openlocfilehash: 7283e4225b75909322fa312583e9f1a0679762e2
ms.sourcegitcommit: 68653db98c5ea7744fd438710248935f70020dfb
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/22/2019
ms.locfileid: "69918392"
---
# <a name="how-to-use-system-fonts-keys"></a>Procedura: Usare le chiavi dei tipi di carattere del sistema
Le risorse di sistema espongono diverse metriche di sistema come risorse per consentire agli sviluppatori di creare oggetti visivi coerenti con le impostazioni di sistema. <xref:System.Windows.SystemFonts>è una classe che contiene sia i valori dei tipi di carattere del sistema che le risorse del tipo di carattere di <xref:System.Windows.SystemFonts.CaptionFontFamily%2A> sistema <xref:System.Windows.SystemFonts.CaptionFontFamilyKey%2A>che vengono associati ai valori, ad esempio e.  
  
 Le metriche dei tipi di carattere del sistema possono essere usate come risorse statiche o dinamiche. Usare una risorsa dinamica per aggiornare automaticamente la metrica del tipo di carattere durante l'esecuzione dell'applicazione; in caso contrario, usare una risorsa statica.  
  
> [!NOTE]
> Per le risorse dinamiche è stata aggiunta la parola *chiave Key* al nome della proprietà.  
  
 L'esempio seguente illustra come accedere alle risorse dinamiche dei tipi di carattere del sistema e usarle per applicare uno stile a un pulsante o personalizzarlo. In [!INCLUDE[TLA2#tla_xaml](../../../../includes/tla2sharptla-xaml-md.md)] questo esempio viene creato uno stile pulsante che <xref:System.Windows.SystemFonts> assegna valori a un pulsante.  
  
## <a name="example"></a>Esempio  
 [!code-xaml[SystemRes_snip#FontDynamicResources](~/samples/snippets/csharp/VS_Snippets_Wpf/SystemRes_snip/CSharp/MyApp.xaml#fontdynamicresources)]  
  
## <a name="see-also"></a>Vedere anche

- [Disegnare un'area con un pennello di sistema](../graphics-multimedia/how-to-paint-an-area-with-a-system-brush.md)
- [Utilizzare SystemParameters](how-to-use-systemparameters.md)
- [Utilizzare la classe SystemFonts](how-to-use-systemfonts.md)
