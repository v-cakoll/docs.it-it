---
title: Cenni preliminari su ClearType
ms.date: 03/30/2017
helpviewer_keywords:
- typography [WPF], ClearType technology
- ClearType [WPF], technology
ms.assetid: 7e2392e0-75dc-463d-a716-908772782431
ms.openlocfilehash: b76c0cb04e5de498374cbf28c8813fe5c95d41ae
ms.sourcegitcommit: 7588136e355e10cbc2582f389c90c127363c02a5
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/12/2020
ms.locfileid: "79186160"
---
# <a name="cleartype-overview"></a>Cenni preliminari su ClearType
In questo argomento viene fornita una panoramica [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)]della tecnologia Microsoft ClearType disponibile nella sezione .  

<a name="overview"></a>
## <a name="technology-overview"></a>Informazioni generali sulla tecnologia  
 ClearType è una tecnologia software sviluppata da Microsoft che migliora la leggibilità del testo sui display LCD (Liquid Crystal Display) esistenti, come schermi di laptop, pocket PC e monitor a pannello piatto.  ClearType funziona accedendo ai singoli elementi striscia di colore verticale in ogni pixel di uno schermo LCD. Prima di ClearType, il più piccolo livello di dettaglio che un computer poteva visualizzare era di un singolo pixel, ma con ClearType in esecuzione su un monitor LCD, ora possiamo visualizzare caratteristiche del testo piccole come una frazione di pixel in larghezza. La risoluzione aggiuntiva aumenta la nitidezza dei piccoli dettagli nella visualizzazione del testo, rendendone più facile la lettura per periodi prolungati.  
  
 Il ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] disponibile in è l'ultima generazione di ClearType che ha diversi miglioramenti sulla versione trovato in Microsoft Windows Graphics Device Interface (GDI).  
  
<a name="sub-pixel_positioning"></a>
## <a name="sub-pixel-positioning"></a>Posizionamento dei subpixel  
 Un miglioramento significativo rispetto alla versione precedente di ClearType è l'uso del posizionamento dei subpixel. A differenza dell'implementazione ClearType presente in [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] GDI, il ClearType trovato in consente ai glifi di iniziare all'interno del pixel e non solo il limite iniziale del pixel. Grazie a questa risoluzione aggiuntiva nel posizionamento dei glifi, la spaziatura e le proporzioni dei glifi risultano più precise e coerenti.  
  
 Nei due esempi seguenti viene mostrato come è possibile inserire i glifi su qualsiasi limite del subpixel se si usa il posizionamento dei subpixel. Il rendering dell'esempio a sinistra viene eseguito utilizzando la versione precedente del renderer ClearType, che non utilizzava il posizionamento dei subpixel. Il rendering dell'esempio a destra viene eseguito utilizzando la nuova versione del renderer ClearType, usando il posizionamento dei subpixel. Notare che il rendering dei caratteri **e** e **l** nell'immagine a destra è leggermente diverso in quanto ognuno inizia in corrispondenza di un subpixel diverso. Quando il testo viene visualizzato sullo schermo con le dimensioni normali, questa differenza non è ben visibile a causa dell'elevato contrasto dell'immagine del glifo Ciò è possibile solo a causa di un sofisticato filtraggio dei colori incorporato in ClearType.  
  
 ![Testo visualizzato con due versioni di ClearType](./media/wcpsdk-mmgraphics-text-cleartype-overview-01.png "wcpsdk_mmgraphics_text_cleartype_overview_01")  
Testo visualizzato con la versione precedente e quella successiva di ClearType  
  
 I due esempi seguenti confrontano l'output del renderer ClearType precedente con la nuova versione del renderer ClearType. Il posizionamento dei subpixel, mostrato a destra, consente di migliorare notevolmente la spaziatura dei tipi sullo schermo, specialmente alle dimensioni più piccole, in cui la differenza tra un subpixel e un pixel intero rappresenta una parte significativa della larghezza del glifo. Notare che la spaziatura tra le lettere è più uniforme nella seconda immagine. Il vantaggio cumulativo del posizionamento dei subpixel all'aspetto generale di una schermata di testo è notevolmente aumentato e rappresenta un'evoluzione significativa nella tecnologia ClearType.  
  
 ![Testo visualizzato con una versione precedente di ClearType](./media/wcpsdk-mmgraphics-text-cleartype-overview-02.png "wcpsdk_mmgraphics_text_cleartype_overview_02")  
Confronto tra il testo visualizzato con la versione precedente di ClearType e quello visualizzato con la versione successiva  
  
<a name="y-direction_antialiasing"></a>
## <a name="y-direction-antialiasing"></a>Anti-aliasing della direzione Y  
 Un altro miglioramento [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] di ClearType in è l'anti-aliasing della direzione y. Il ClearType in GDI senza anti-aliasing della direzione y fornisce una migliore risoluzione sull'asse x ma non sull'asse y. Nelle parti superiori e inferiori delle curve poco pronunciate, i bordi frastagliati riducono la leggibilità.  
  
 L'esempio seguente mostra l'effetto dell'assenza di anti-aliasing della direzione y. In questo caso, i bordi frastagliati nella parte superiore e inferiore della lettera sono chiaramente visibili.  
  
 ![Testo con bordi frastagliati su curve poco pronunciate](./media/wcpsdk-mmgraphics-text-cleartype-overview-03.png "wcpsdk_mmgraphics_text_cleartype_overview_03")  
Testo con bordi frastagliati su curve poco pronunciate  
  
 ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in fornisce l'antialiasing a livello di direzione y per smussare eventuali bordi frastagliati. Tale funzionalità è particolarmente importante per migliorare la leggibilità delle lingue asiatiche, nelle quali gli ideogrammi presentano un quantità quasi uguale di curve poco pronunciate orizzontali e verticali.  
  
 L'esempio seguente illustra gli effetti dell'anti-aliasing della direzione Y. In questo caso, la parte superiore e quella inferiore della lettera mostrano una curva uniforme.  
  
 ![Testo con anti&#45;aliasing della direzione y ClearType](./media/wcpsdk-mmgraphics-text-cleartype-overview-04.png "wcpsdk_mmgraphics_text_cleartype_overview_04")  
Testo con anti-aliasing della direzione y ClearType  
  
<a name="hardware_acceleration"></a>
## <a name="hardware-acceleration"></a>Accelerazione hardware  
 ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in può sfruttare l'accelerazione hardware per migliorare le prestazioni e ridurre il carico della CPU e i requisiti di memoria di sistema. Utilizzando i pixel shader e la memoria video di una scheda grafica, ClearType fornisce un rendering più veloce del testo, in particolare quando viene utilizzata l'animazione.  
  
 ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in non modifica le impostazioni ClearType a livello di sistema. La disabilitazione di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] ClearType in Windows imposta l'antialiasing in modalità scala di grigi. Inoltre, ClearType [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] in non modifica le impostazioni di [ClearType Tuner PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx).  
  
 Una delle decisioni relative alla progettazione dell'architettura di [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] consiste nel disporre di monitor DPI a risoluzione più elevata con supporto migliorato del layout indipendente dalla risoluzione, di diffusione sempre maggiore. Come conseguenza di tale scelta, [!INCLUDE[TLA#tla_winclient](../../../../includes/tlasharptla-winclient-md.md)] non supporta il rendering del testo con anti-aliasing o le bitmap in alcuni tipi di carattere asiatici in quanto entrambi sono dipendenti dalla risoluzione.  
  
<a name="further_information"></a>
## <a name="further-information"></a>Ulteriori informazioni  
 [Informazioni su ClearType](https://www.microsoft.com/typography/ClearTypeInfo.mspx)  
  
 [ClearType Tuner PowerToy](https://www.microsoft.com/typography/ClearTypePowerToy.mspx)  
  
## <a name="see-also"></a>Vedere anche

- [Impostazioni del Registro di sistema ClearType](cleartype-registry-settings.md)
