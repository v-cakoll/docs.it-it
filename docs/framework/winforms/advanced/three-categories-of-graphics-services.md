---
title: Tre categorie di servizi grafici
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: fa7391ef0f7170ddb9d9d24aa5a1a03635bf46e0
ms.sourcegitcommit: e48a54ebe62e874500a7043f6ee0b77a744d55b4
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/26/2020
ms.locfileid: "80291734"
---
# <a name="three-categories-of-graphics-services"></a>Tre categorie di servizi grafici
Le offerte grafiche in Windows Form rientrano nelle tre categorie generali seguenti:The graphics offerings in Windows Forms fall into the following three broad categories:  
  
- Grafica vettoriale bidimensionale (2D)  
  
- Creazione delle immagini  
  
- Opzioni tipografiche  
  
## <a name="2d-vector-graphics"></a>Grafica vettoriale 2D  
 La grafica vettoriale bidimensionale, ad esempio linee, curve e figure, è costituita da primitive specificate da insiemi di punti in un sistema di coordinate. Ad esempio, una linea retta viene specificata dai due punti finali e un rettangolo viene specificato da un punto che indica la posizione dell'angolo superiore sinistro e da una coppia di numeri che ne indicano la larghezza e l'altezza. Un percorso semplice è specificato da una matrice di punti collegati da linee rette. Una spline di Bézier è una curva sofisticata specificata da quattro punti di controllo.  
  
 In GDIè sono disponibili classi e strutture che archiviano informazioni sulle primitive stesse, classi che archiviano informazioni su come verranno disegnate le primitive e classi che effettivamente eseguiranno il disegno. Ad esempio, <xref:System.Drawing.Rectangle> la struttura archivia la posizione e le dimensioni di un rettangolo; la <xref:System.Drawing.Pen> classe memorizza informazioni sul colore della linea, lo spessore della linea e lo stile della linea; e <xref:System.Drawing.Graphics> la classe dispone di metodi per disegnare linee, rettangoli, tracciati e altre figure. Ci sono <xref:System.Drawing.Brush> anche diverse classi che memorizzano informazioni su come figure chiuse e percorsi saranno riempiti con colori o motivi.  
  
 È possibile registrare un'immagine vettoriale, ovvero una sequenza di comandi grafici, in un metafile. La classe per <xref:System.Drawing.Imaging.Metafile> la registrazione, la visualizzazione e il salvataggio dei metafile è disponibile in GDIè. Con <xref:System.Drawing.Imaging.MetafileHeader> le <xref:System.Drawing.Imaging.MetaHeader> classi e , è possibile esaminare i dati archiviati in un'intestazione metafile.  
  
## <a name="imaging"></a>Creazione delle immagini  
 Alcuni tipi di immagini sono difficili o impossibili da visualizzare con le tecniche di grafica vettoriale. Ad esempio, le immagini sui pulsanti della barra degli strumenti e le immagini visualizzate come icone sono difficili da specificare come raccolte di linee e curve. Una fotografia digitale ad alta risoluzione di uno stadio di baseball affollato è ancora più difficile da creare con tecniche vettoriali. Le immagini di questo tipo vengono memorizzate come bitmap, ovvero matrici di numeri che rappresentano i colori dei singoli punti sullo schermo. In GDIè è disponibile la <xref:System.Drawing.Bitmap> classe per la visualizzazione, la modifica e il salvataggio delle bitmap.  
  
## <a name="typography"></a>Opzioni tipografiche  
 La tipografia è la visualizzazione del testo in una varietà di tipi di carattere, dimensioni e stili. Per questa complessa attività, GDIè fornisce un ampio supporto per questa complessa attività. Una delle nuove funzionalità di GDI è l'antialiasing dei subpixel, che conferisce al testo sottoposto a rendering su uno schermo LCD un aspetto più uniforme.  
  
 Inoltre, Windows Form offre la possibilità di disegnare <xref:System.Windows.Forms.TextRenderer> testo con funzionalità GDI nella relativa classe.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulla grafica](graphics-overview-windows-forms.md)
- [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)
- [Utilizzo di classi grafiche gestite](using-managed-graphics-classes.md)
