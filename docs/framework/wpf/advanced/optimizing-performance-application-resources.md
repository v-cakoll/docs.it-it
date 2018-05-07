---
title: 'Ottimizzazione delle prestazioni: risorse di applicazioni'
ms.date: 03/30/2017
helpviewer_keywords:
- application resources [WPF], performance
- resources [WPF], performance
- static resources [WPF]
- sharing resources [WPF]
- brushes [WPF], performance
- sharing brushes without copying [WPF]
ms.assetid: 62b88488-c08e-4804-b7de-a1c34fbe929c
ms.openlocfilehash: 53e906f31f32fb0f1df3f8d986daa0ae95ea9e4c
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="optimizing-performance-application-resources"></a>Ottimizzazione delle prestazioni: risorse di applicazioni
[!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] Consente di condividere le risorse dell'applicazione in modo che è possibile supportare un comportamento coerente tra tipi simili di elementi. Questo argomento vengono fornite alcune indicazioni che consentono di migliorare le prestazioni delle applicazioni.  
  
 Per altre informazioni sulle risorse, vedere [Risorse XAML](../../../../docs/framework/wpf/advanced/xaml-resources.md).  
  
## <a name="sharing-resources"></a>La condivisione delle risorse  
 Se l'applicazione utilizza controlli personalizzati e definisce le risorse in un <xref:System.Windows.ResourceDictionary> (o nodo di risorse XAML), è consigliabile definire le risorse a livello di <xref:System.Windows.Application> o <xref:System.Windows.Window> oggetto livello oppure definirle nel tema predefinito per il controlli personalizzati. Definizione delle risorse in un controllo personalizzato <xref:System.Windows.ResourceDictionary> impone un impatto sulle prestazioni per ogni istanza del controllo. Ad esempio, se sono presenti operazioni di pennello a prestazioni intensive definite come parte della definizione di risorsa di un controllo personalizzato e numero di istanze del controllo personalizzato, il set di lavoro dell'applicazione aumenterà in modo significativo.  
  
 Per illustrare questo punto, considerare quanto segue. Si supponga che si sta sviluppando un gioco di smart card tramite [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Per la maggior parte dei giochi di carte, è necessario 52 carte con 52 facce diverse. Si decide di implementare un controllo personalizzato di smart card e si definiscono 52 pennelli (ognuno dei quali rappresenta un tipo di carattere card) nelle risorse del controllo personalizzato delle carte. Nell'applicazione principale, si creano inizialmente 52 istanze di tale controllo personalizzato. Ogni istanza del controllo personalizzato scheda genera 52 istanze di <xref:System.Windows.Media.Brush> gli oggetti, che offre un totale di 52 * 52 <xref:System.Windows.Media.Brush> oggetti nell'applicazione. Spostando i pennelli esaurito le risorse di controllo personalizzato di smart card per il <xref:System.Windows.Application> o <xref:System.Windows.Window> livello di oggetto, oppure definendole nel tema predefinito per il controllo personalizzato, si riduce il working set dell'applicazione, poiché si condividono i 52 pennelli tra 52 istanze del controllo scheda.  
  
## <a name="sharing-a-brush-without-copying"></a>Condivisione di un pennello senza copia  
 Se si dispone di più elementi che utilizzano lo stesso <xref:System.Windows.Media.Brush> dell'oggetto, definire il pennello come una risorsa e fare riferimento, anziché definire il pennello inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)]. Questo metodo verrà creata un'istanza e riutilizzare, mentre la definizione di pennelli inline in [!INCLUDE[TLA#tla_titlexaml](../../../../includes/tlasharptla-titlexaml-md.md)] crea una nuova istanza per ogni elemento.  
  
 L'esempio di codice seguente viene illustrato questo punto:  
  
 [!code-xaml[Performance#PerformanceSnippet7](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/BrushResource.xaml#performancesnippet7)]  
  
## <a name="use-static-resources-when-possible"></a>Utilizzare risorse statiche quando possibile  
 Una risorsa statica fornisce un valore per tutti gli attributi di proprietà XAML eseguendo la ricerca di un riferimento a una risorsa già definita. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di compilazione.  
  
 Una risorsa dinamica, d'altra parte, creare un'espressione temporanea durante la compilazione iniziale, pertanto viene rinviata ricerca per le risorse fino a quando il valore della risorsa richiesta è effettivamente necessario per costruire un oggetto. Il comportamento di ricerca per tale risorsa è analogo alla ricerca in fase di esecuzione, che impone un impatto sulle prestazioni. Utilizzare le risorse statiche ogni volta che è possibile in un'applicazione, con le risorse dinamiche solo quando necessario.  
  
 L'esempio di codice seguente viene illustrato l'utilizzo di entrambi i tipi di risorse:  
  
 [!code-xaml[Performance#PerformanceSnippet8](../../../../samples/snippets/csharp/VS_Snippets_Wpf/Performance/CSharp/DynamicResource.xaml#performancesnippet8)]  
  
## <a name="see-also"></a>Vedere anche  
 [Ottimizzazione delle prestazioni di applicazioni WPF](../../../../docs/framework/wpf/advanced/optimizing-wpf-application-performance.md)  
 [Pianificazione delle prestazioni dell'applicazione](../../../../docs/framework/wpf/advanced/planning-for-application-performance.md)  
 [Sfruttare appieno l'hardware](../../../../docs/framework/wpf/advanced/optimizing-performance-taking-advantage-of-hardware.md)  
 [Ottimizzazione delle prestazioni: layout e progettazione](../../../../docs/framework/wpf/advanced/optimizing-performance-layout-and-design.md)  
 [Grafica bidimensionale e creazione di immagini](../../../../docs/framework/wpf/advanced/optimizing-performance-2d-graphics-and-imaging.md)  
 [Comportamento dell'oggetto](../../../../docs/framework/wpf/advanced/optimizing-performance-object-behavior.md)  
 [per](../../../../docs/framework/wpf/advanced/optimizing-performance-text.md)  
 [Data binding](../../../../docs/framework/wpf/advanced/optimizing-performance-data-binding.md)  
 [Altri suggerimenti relativi alle prestazioni](../../../../docs/framework/wpf/advanced/optimizing-performance-other-recommendations.md)
