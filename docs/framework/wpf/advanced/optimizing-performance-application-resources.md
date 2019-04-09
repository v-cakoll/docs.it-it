---
title: "Ottimizzazione delle prestazioni: Risorse dell'applicazione"
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 362d0f0fd3282365e5e05dcd43c49a9fd2ddc9a7
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59139425"
---
# <a name="optimizing-performance-application-resources"></a>Ottimizzazione delle prestazioni: Risorse dell'applicazione
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Consente di condividere le risorse dell'applicazione in modo che sia possibile supportare un aspetto coerente o il comportamento tra elementi di tipi simili. Questo argomento vengono elencati alcuni suggerimenti in questa area che consentono di migliorare le prestazioni delle applicazioni.  
  
 Per altre informazioni sulle risorse, vedere [Risorse XAML](xaml-resources.md).  
  
## <a name="sharing-resources"></a>La condivisione delle risorse  
 Se l'applicazione usa i controlli personalizzati e definisce le risorse in un <xref:System.Windows.ResourceDictionary> (o nodo risorse XAML), è consigliabile definire le risorse a livello di <xref:System.Windows.Application> o <xref:System.Windows.Window> a livello dell'oggetto oppure definirli nel tema predefinito per il controlli personalizzati. Definizione delle risorse in un controllo personalizzato <xref:System.Windows.ResourceDictionary> comporta un impatto sulle prestazioni per ogni istanza del controllo. Ad esempio, se hai definito come parte della definizione di risorsa di un controllo personalizzato e numero di istanze del controllo personalizzato operazioni pennello a prestazioni intensive, working set dell'applicazione aumenterà in modo significativo.  
  
 Per illustrare questo punto, considerare quanto segue. Si supponga che si sta sviluppando un gioco di carte tramite [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per la maggior parte dei giochi di carte, è necessario 52 carte con 52 facce diverse. Si decide di implementare un controllo personalizzato di smart card e definire i 52 pennelli (ognuno dei quali rappresenta un viso smart card) nelle risorse del controllo personalizzato delle carte. Nell'applicazione principale, si creano inizialmente 52 istanze di tale controllo personalizzato. Ogni istanza del controllo personalizzato card genera 52 istanze di <xref:System.Windows.Media.Brush> oggetti, che ti offre un totale di 52 * 52 <xref:System.Windows.Media.Brush> oggetti nell'applicazione. Spostando i pennelli esaurisce le risorse di controllo personalizzato di smart card per il <xref:System.Windows.Application> o <xref:System.Windows.Window> a livello di oggetto, oppure definendole nel tema predefinito per il controllo personalizzato, si riduce il working set dell'applicazione, poiché ora si condividono i 52 pennelli tra le 52 istanze del controllo scheda.  
  
## <a name="sharing-a-brush-without-copying"></a>Condivisione di un pennello senza copia  
 Se si dispone di più elementi che utilizzano lo stesso <xref:System.Windows.Media.Brush> dell'oggetto, definire il pennello come una risorsa e fare riferimento, invece di definire il pennello inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Questo metodo crea un'istanza e riutilizzare, mentre la definizione inline di pennelli in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] crea una nuova istanza per ogni elemento.  
  
 L'esempio di markup seguente illustra questo punto:  
  
 [!code-xaml[Performance#PerformanceSnippet7](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Usare le risorse statiche, quando possibile  
 Una risorsa statica fornisce un valore per tutti gli attributi di proprietà XAML eseguendo la ricerca di un riferimento a una risorsa già definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di compilazione.  
  
 Una risorsa dinamica, d'altra parte, creare un'espressione temporanea durante la compilazione iniziale, pertanto viene rinviata ricerca per le risorse fino a quando il valore della risorsa richiesta è effettivamente necessario per costruire un oggetto. Il comportamento di ricerca per tale risorsa è analogo alla ricerca di run-time, che comporta un impatto sulle prestazioni. Usare le risorse statiche ogni volta che è possibile nell'applicazione, usando le risorse dinamiche solo quando necessario.  
  
 L'esempio di markup seguente illustra l'uso di entrambi i tipi di risorse:  
  
 [!code-xaml[Performance#PerformanceSnippet8](~/samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Vedere anche

- [Ottimizzazione delle prestazioni di applicazioni WPF](optimizing-wpf-application-performance.md)
- [Pianificazione delle prestazioni dell'applicazione](planning-for-application-performance.md)
- [Sfruttare appieno l'hardware](optimizing-performance-taking-advantage-of-hardware.md)
- [Layout e progettazione](optimizing-performance-layout-and-design.md)
- [Grafica 2D e creazione di immagini](optimizing-performance-2d-graphics-and-imaging.md)
- [Comportamento degli oggetti](optimizing-performance-object-behavior.md)
- [Testo](optimizing-performance-text.md)
- [Data binding](optimizing-performance-data-binding.md)
- [Altri suggerimenti relativi alle prestazioni](optimizing-performance-other-recommendations.md)
