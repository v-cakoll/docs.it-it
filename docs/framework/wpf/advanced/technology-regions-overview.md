---
title: Cenni preliminari sulle aree di tecnologia
ms.date: 03/30/2017
helpviewer_keywords:
- window regions [WPF]
- Win32 code [WPF], WPF interoperation
- Win32 code [WPF], airspace
- airspace [WPF]
- interoperability [WPF], airspace
- Win32 code [WPF], window regions
ms.assetid: b7cc350f-b9e2-48b1-be14-60f3d853222e
ms.openlocfilehash: 4f1489065a70065700d2f8ceb974e66ecceeebd0
ms.sourcegitcommit: 77e33b682db39955e331b8e8eda4ef1925a24e78
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 08/29/2019
ms.locfileid: "70133807"
---
# <a name="technology-regions-overview"></a>Cenni preliminari sulle aree di tecnologia
Se in un'applicazione si usano più tecnologie di presentazione, ad esempio WPF, Win32 o DirectX, queste devono condividere le aree di rendering all'interno di una finestra comune di primo livello. Questo argomento descrive i problemi che potrebbero influire sulla presentazione e l'input per l'applicazione di interoperatività WPF.  
  
## <a name="regions"></a>Aree  
 È possibile partire dal concetto che, all'interno di una finestra di primo livello, ogni HWND che include una delle tecnologie di un'applicazione di interoperatività ha una propria area, anche detta "spazio aereo". Ogni pixel all'interno della finestra appartiene esattamente a un HWND e ne costituisce l'area. Per essere precisi, se esistono più HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], esisteranno più aree di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ma ai fini di questa spiegazione si può presupporre che ne esista uno solo. Il concetto di area implica che tutti i livelli o le altre finestre che provano a eseguire il rendering sopra tale pixel nel corso della durata dell'applicazione devono essere parte della stessa tecnologia a livello di rendering. Il tentativo di eseguire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] il rendering [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] dei pixel su conduce a risultati indesiderati e non è consentito quanto più possibile tramite le API di interoperatività.  
  
### <a name="region-examples"></a>Esempi di area  
 Nella figura seguente viene illustrata un'applicazione [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]che combina, DirectX [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]e. Ogni tecnologia usa un set di pixel specifico distinto, non sovrapposto, per cui non esistono problemi di area.  
  
 ![Esempio di applicazione che combina Win32, DirectX e WPF.](./media/technology-regions-overview/win32-directx-windows-presentation-foundation-application.png)  
  
 Si supponga che questa applicazione usi la posizione del puntatore del mouse per creare un'animazione che prova a eseguire il rendering su una qualsiasi di queste tre aree. Indipendentemente dalla tecnologia responsabile dell'animazione stessa, quella tecnologia violerebbe l'area delle altre due. La figura seguente illustra il tentativo di rendering di un cerchio WPF in un'area di Win32.  
  
 ![Tentativo di eseguire il rendering di un cerchio WPF su un'area Win32.](./media/technology-regions-overview/render-windows-presentation-foundation-circle-over-win32-region.png)  
  
 Un'altra violazione si verifica quando si prova a usare la trasparenza o la fusione alfa tra tecnologie diverse.  Nella figura seguente la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] casella viola le [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] aree e DirectX. Poiché i pixel in [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] tale casella sono semi-trasparenti, devono essere di proprietà congiuntamente da DirectX e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], il che non è possibile.  Pertanto, si tratta di un'altra violazione che rende la compilazione impossibile.  
  
 ![Diagramma che mostra una finestra WPF che viola le aree Win32 e DirectX.](./media/technology-regions-overview/windows-foundation-presentation-box-violate-win32-directx-region.png)  
  
 Nei tre esempi precedenti vengono usate aree rettangolari, ma si possono usare altre forme.  Ad esempio, un'area può presentare un foro. La figura seguente mostra un' [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] area con un foro rettangolare [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] , ovvero la dimensione delle aree e DirectX combinate.  
  
 ![Diagramma che mostra un'area Win32 con un foro rettangolare.](./media/technology-regions-overview/win32-region-rectangular-hole.png)  
  
 Le aree possono essere anche non rettangolari o di qualsiasi forma che possa essere descritta da un tipo HRGN [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] (area).  
  
 ![Diagramma che mostra un'area non rettangolare.](./media/technology-regions-overview/nonrectangular-win32-region.png)  
  
## <a name="transparency-and-top-level-windows"></a>Trasparenza e finestre di primo livello  
 La funzionalità Gestione finestre di Windows in realtà elabora solo HWND [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)]. Pertanto, ogni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> è un HWND. <xref:System.Windows.Window> HWND deve rispettare le regole generali per qualsiasi HWND. All'interno di tale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] HWND, il codice può eseguire [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] qualsiasi tipo di supporto delle API complessive. Per le interazioni con altri HWND sul desktop, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] deve attenersi alle regole di elaborazione e di rendering di [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)].  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]supporta le finestre non rettangolari usando [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] le API, HRGNs per le finestre non rettangolari e le finestre sovrapposte per un Alpha per pixel.  
  
 La costante alfa e le chiavi di colore non sono supportate.  Le funzionalità delle finestre sovrapposte [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] variano in base alla piattaforma.  
  
 Le finestre sovrapposte possono rendere semitrasparente l'intera finestra specificando un valore alfa da applicare a tutti i pixel della finestra.  [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] supporta in effetti il valore alfa per pixel, che è però molto difficile da usare nella pratica in quanto in questa modalità è necessario disegnare manualmente ogni HWND figlio, inclusi finestre di dialogo ed elenchi a discesa.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]supporta HRGNs; non sono tuttavia disponibili API gestite per questa funzionalità. È possibile usare Platform Invoke e <xref:System.Windows.Interop.HwndSource> per chiamare le API [!INCLUDE[TLA2#tla_win32](../../../../includes/tla2sharptla-win32-md.md)] pertinenti. Per altre informazioni, vedere [Chiamata di funzioni native da codice gestito](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 Le finestre sovrapposte di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno funzionalità diverse in sistemi operativi diversi. Questo perché [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa DirectX per eseguire il rendering e le finestre sovrapposte sono state progettate principalmente per il rendering GDI, non per il rendering DirectX.  
  
- WPF supporta le finestre sovrapposte con accelerazione hardware.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non supporta chiavi di colore trasparenza in quanto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non può garantire di eseguire il rendering del colore esatto richiesto, in particolare quando il rendering usa l'accelerazione hardware.  
  
## <a name="see-also"></a>Vedere anche

- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Procedura dettagliata: Hosting di un Clock WPF in Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hosting di contenuto Win32 in WPF](hosting-win32-content-in-wpf.md)
