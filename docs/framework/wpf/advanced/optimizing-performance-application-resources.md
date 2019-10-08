---
title: 'Ottimizzazione delle prestazioni: Risorse delle applicazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 759d02afe1934d2ace4ed226d5d911db2d676d98
ms.sourcegitcommit: eff6adb61852369ab690f3f047818c90580e7eb1
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 10/07/2019
ms.locfileid: "72005035"
---
# <a name="optimizing-performance-application-resources"></a>Ottimizzazione delle prestazioni: Risorse delle applicazioni
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] consente di condividere le risorse dell'applicazione in modo che sia possibile supportare un aspetto o un comportamento coerente in elementi tipizzati simili. In questo argomento vengono fornite alcune raccomandazioni in questa area che consentono di migliorare le prestazioni delle applicazioni.  
  
 Per altre informazioni sulle risorse, vedere [Risorse XAML](xaml-resources.md).  
  
## <a name="sharing-resources"></a>Condivisione di risorse  
 Se l'applicazione usa controlli personalizzati e definisce le risorse in un <xref:System.Windows.ResourceDictionary> (o nodo delle risorse XAML), è consigliabile definire le risorse a livello di oggetto <xref:System.Windows.Application> o <xref:System.Windows.Window> oppure definirle nel tema predefinito per i controlli personalizzati. La definizione delle risorse nel <xref:System.Windows.ResourceDictionary> di un controllo personalizzato impone un effetto sulle prestazioni per ogni istanza di tale controllo. Se, ad esempio, si dispone di operazioni pennello a elevato utilizzo di prestazioni definite come parte della definizione di risorsa di un controllo personalizzato e di molte istanze del controllo personalizzato, l'working set dell'applicazione aumenterà significativamente.  
  
 Per illustrare questo punto, tenere presente quanto segue. Supponiamo che si stia sviluppando un gioco di carte usando [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per la maggior parte dei giochi di carte sono necessarie 52 schede con 52 visi differenti. Si decide di implementare un controllo personalizzato di una scheda e si definiscono 52 pennelli (ognuno dei quali rappresenta un volto di scheda) nelle risorse del controllo personalizzato della scheda. Nell'applicazione principale si creano inizialmente 52 istanze di questo controllo personalizzato della scheda. Ogni istanza del controllo personalizzato scheda genera 52 istanze di oggetti <xref:System.Windows.Media.Brush>, che fornisce un totale di 52 * 52 <xref:System.Windows.Media.Brush> oggetti nell'applicazione. Spostando i pennelli fuori dalla scheda risorse di controllo personalizzate per il livello di oggetto <xref:System.Windows.Application> o <xref:System.Windows.Window> oppure definendoli nel tema predefinito per il controllo personalizzato, si riduce il working set dell'applicazione, perché ora si condividono i pennelli 52 tra 52 istanze del controllo scheda.  
  
## <a name="sharing-a-brush-without-copying"></a>Condivisione di un pennello senza copia  
 Se sono presenti più elementi che usano lo stesso oggetto <xref:System.Windows.Media.Brush>, definire il pennello come risorsa e farvi riferimento, anziché definire il pennello inline in XAML. Questo metodo creerà un'istanza e la riutilizzerà, mentre la definizione dei pennelli inline in XAML crea una nuova istanza per ogni elemento.  
  
 Nell'esempio di markup seguente viene illustrato questo punto:  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Usare risorse statiche quando possibile  
 Una risorsa statica fornisce un valore per qualsiasi attributo di proprietà XAML cercando un riferimento a una risorsa già definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di compilazione.  
  
 Una risorsa dinamica, d'altra parte, creerà un'espressione temporanea durante la compilazione iniziale e quindi rinvia la ricerca delle risorse finché il valore della risorsa richiesta non è effettivamente necessario per costruire un oggetto. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione, che impone un effetto sulle prestazioni. Usare le risorse statiche laddove possibile nell'applicazione, usando risorse dinamiche solo quando necessario.  
  
 L'esempio di markup seguente illustra l'uso di entrambi i tipi di risorse:  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Ottimizzazione delle prestazioni: layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica bidimensionale e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento dell'oggetto](optimizing-performance-object-behavior.md)
- [per](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
