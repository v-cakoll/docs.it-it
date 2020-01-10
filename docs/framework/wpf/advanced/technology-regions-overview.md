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
ms.openlocfilehash: 0b6ad222737f992da3074770fb5a2bff17860c00
ms.sourcegitcommit: 9a97c76e141333394676bc5d264c6624b6f45bcf
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 01/08/2020
ms.locfileid: "75740296"
---
# <a name="technology-regions-overview"></a>Cenni preliminari sulle aree di tecnologia
Se in un'applicazione si usano più tecnologie di presentazione, ad esempio WPF, Win32 o DirectX, queste devono condividere le aree di rendering all'interno di una finestra comune di primo livello. Questo argomento descrive i problemi che potrebbero influire sulla presentazione e l'input per l'applicazione di interoperatività WPF.  
  
## <a name="regions"></a>Aree  
 È possibile partire dal concetto che, all'interno di una finestra di primo livello, ogni HWND che include una delle tecnologie di un'applicazione di interoperatività ha una propria area, anche detta "spazio aereo". Ogni pixel all'interno della finestra appartiene esattamente a un HWND e ne costituisce l'area. Per essere precisi, se esistono più HWND [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], esisteranno più aree di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], ma ai fini di questa spiegazione si può presupporre che ne esista uno solo. Il concetto di area implica che tutti i livelli o le altre finestre che provano a eseguire il rendering sopra tale pixel nel corso della durata dell'applicazione devono essere parte della stessa tecnologia a livello di rendering. Il tentativo di eseguire il rendering di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] pixel su Win32 comporta risultati indesiderati e non è consentito quanto più possibile tramite le API di interoperatività.  
  
### <a name="region-examples"></a>Esempi di area  
 Nella figura seguente viene illustrata un'applicazione che combina Win32, DirectX e [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)]. Ogni tecnologia usa un set di pixel specifico distinto, non sovrapposto, per cui non esistono problemi di area.  
  
 ![Esempio di applicazione che combina Win32, DirectX e WPF.](./media/technology-regions-overview/win32-directx-windows-presentation-foundation-application.png)  
  
 Si supponga che questa applicazione usi la posizione del puntatore del mouse per creare un'animazione che prova a eseguire il rendering su una qualsiasi di queste tre aree. Indipendentemente dalla tecnologia responsabile dell'animazione stessa, quella tecnologia violerebbe l'area delle altre due. La figura seguente illustra il tentativo di rendering di un cerchio WPF in un'area di Win32.  
  
 ![Tentativo di eseguire il rendering di un cerchio WPF su un'area Win32.](./media/technology-regions-overview/render-windows-presentation-foundation-circle-over-win32-region.png)  
  
 Un'altra violazione si verifica quando si prova a usare la trasparenza o la fusione alfa tra tecnologie diverse.  Nella figura seguente la [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] box viola le aree Win32 e DirectX. Poiché i pixel in tale [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] box sono semitrasparenti, devono essere di proprietà congiunta sia con DirectX che con [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)], operazione che non è possibile.  Pertanto, si tratta di un'altra violazione che rende la compilazione impossibile.  
  
 ![Diagramma che mostra una finestra WPF che viola le aree Win32 e DirectX.](./media/technology-regions-overview/windows-foundation-presentation-box-violate-win32-directx-region.png)  
  
 Nei tre esempi precedenti vengono usate aree rettangolari, ma si possono usare altre forme.  Ad esempio, un'area può presentare un foro. La figura seguente mostra un'area Win32 con un foro rettangolare, ovvero la dimensione delle aree [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] e DirectX combinate.  
  
 ![Diagramma che mostra un'area Win32 con un foro rettangolare.](./media/technology-regions-overview/win32-region-rectangular-hole.png)  
  
 Le aree possono anche essere completamente non rettangolari o qualsiasi forma descrittiva da un HRGN Win32 (regione).  
  
 ![Diagramma che mostra un'area non rettangolare.](./media/technology-regions-overview/nonrectangular-win32-region.png)  
  
## <a name="transparency-and-top-level-windows"></a>Trasparenza e finestre di primo livello  
 Gestione finestre di Windows elabora solo gli HWND Win32. Pertanto, ogni [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] <xref:System.Windows.Window> è un HWND. Il <xref:System.Windows.Window> HWND deve rispettare le regole generali per qualsiasi HWND. All'interno di tale HWND, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] codice può eseguire qualsiasi tipo di supporto per le API [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] complessive. Tuttavia, per le interazioni con altri HWND sul desktop, [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] necessario rispettare le regole di rendering e di elaborazione di Win32.  [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta le finestre non rettangolari usando le API Win32, HRGNs per le finestre non rettangolari e le finestre sovrapposte per un Alpha per pixel.  
  
 La costante alfa e le chiavi di colore non sono supportate.  Le funzionalità della finestra sovrapposta Win32 variano in base alla piattaforma.  
  
 Le finestre sovrapposte possono rendere semitrasparente l'intera finestra specificando un valore alfa da applicare a tutti i pixel della finestra.  Win32 supporta in realtà l'alfa per pixel, ma è molto difficile da usare nei programmi pratici perché in questa modalità è necessario creare manualmente qualsiasi HWND figlio, inclusi i dialoghi e i menu a discesa.  
  
 [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] supporta HRGNs; non sono tuttavia disponibili API gestite per questa funzionalità. È possibile utilizzare platform invoke e <xref:System.Windows.Interop.HwndSource> per chiamare le API Win32 pertinenti. Per altre informazioni, vedere [Chiamata di funzioni native da codice gestito](/cpp/dotnet/calling-native-functions-from-managed-code).  
  
 Le finestre sovrapposte di [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] hanno funzionalità diverse in sistemi operativi diversi. Questo perché [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] usa DirectX per eseguire il rendering e le finestre sovrapposte sono state progettate principalmente per il rendering GDI, non per il rendering DirectX.  
  
- WPF supporta le finestre sovrapposte con accelerazione hardware.  
  
- [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non supporta chiavi di colore trasparenza in quanto [!INCLUDE[TLA2#tla_winclient](../../../../includes/tla2sharptla-winclient-md.md)] non può garantire di eseguire il rendering del colore esatto richiesto, in particolare quando il rendering usa l'accelerazione hardware.  
  
## <a name="see-also"></a>Vedere anche

- [Interoperatività di WPF e Win32](wpf-and-win32-interoperation.md)
- [Procedura dettagliata: Hosting di un oggetto Clock WPF in Win32](walkthrough-hosting-a-wpf-clock-in-win32.md)
- [Hosting di contenuto Win32 in WPF](hosting-win32-content-in-wpf.md)
