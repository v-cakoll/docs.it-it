---
title: Tre categorie di servizi grafici
ms.date: 03/30/2017
helpviewer_keywords:
- imaging
- graphics [Windows Forms], categories
- 2-D vector graphics
- vector graphics
- typography
ms.assetid: 068c0ef3-f6ee-4d58-a7b6-eb2531ead408
ms.openlocfilehash: 5621a2c0bba2e922e62006feba9ca0381181c780
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="three-categories-of-graphics-services"></a>Tre categorie di servizi grafici
Le offerte di grafica in Windows Form rientrano in tre categorie generali seguenti:  
  
-   Grafica vettoriale bidimensionale di (2-D)  
  
-   Creazione dell'immagine  
  
-   Opzioni tipografiche  
  
## <a name="2-d-vector-graphics"></a>Grafica vettoriale 2D  
 Grafica vettoriale bidimensionale è tipi primitivi; ad esempio linee, curve e figure; dal set di punti in un sistema di coordinate specificati. Ad esempio, una linea retta specificata dal relativo due endpoint, e un rettangolo specificato da un punto in cui la posizione dell'angolo superiore sinistro e una coppia di numeri che ne indicano la larghezza e altezza. Un semplice percorso viene specificato da una matrice di punti che sono connessi tramite linee rette. Una spline di Bézier è una sofisticata curva specificata da quattro punti di controllo.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce classi e strutture che archiviano informazioni sulle primitive autonomamente, le classi che archiviano informazioni sul modo in cui verranno disegnate le primitive e le classi che effettivamente svolgono il disegno. Ad esempio, il <xref:System.Drawing.Rectangle> struttura consente di archiviare la posizione e dimensioni di un rettangolo; il <xref:System.Drawing.Pen> classe archivia le informazioni relative a colore, larghezza di riga e stile di linea e <xref:System.Drawing.Graphics> classe dispone di metodi per disegnare linee, rettangoli, percorsi, e altre figure. Esistono inoltre alcune <xref:System.Drawing.Brush> le classi che contengono informazioni sulla modalità chiuso cifre e i percorsi verranno completati con colori o motivi.  
  
 È possibile registrare un'immagine del vettore, che è una sequenza di comandi di grafica, in un metafile. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce la <xref:System.Drawing.Imaging.Metafile> classe per la registrazione, la visualizzazione e il salvataggio di metafile. Con il <xref:System.Drawing.Imaging.MetafileHeader> e <xref:System.Drawing.Imaging.MetaHeader> classi, è possibile controllare i dati archiviati in un'intestazione del metafile.  
  
## <a name="imaging"></a>Creazione dell'immagine  
 Alcuni tipi di immagini sono difficili o impossibili da visualizzare con le tecniche di grafica vettoriale. Ad esempio, le immagini dei pulsanti della barra degli strumenti e le immagini che vengono visualizzati come icone sono difficili da specificare come raccolte di linee e curve. Una foto digitale ad alta risoluzione di un stadio baseball talmente è ancora più difficile da creare con le tecniche di vettore. Le immagini di questo tipo vengono archiviate come bitmap, matrici di numeri che rappresentano i colori dei singoli punti sullo schermo. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce la <xref:System.Drawing.Bitmap> classe per la visualizzazione, la modifica e salvataggio di bitmap.  
  
## <a name="typography"></a>Opzioni tipografiche  
 Tipografia è la visualizzazione del testo in una vasta gamma di tipi di carattere, dimensioni e stili. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce un supporto completo per questa attività complessa. Una delle nuove funzionalità di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] anti-aliasing subpixel, che restituisce testo rendering in una schermata LCD un aspetto più uniforme.  
  
 Inoltre, Windows Form consente di disegnare testo con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funzionalità relativo <xref:System.Windows.Forms.TextRenderer> classe.  
  
## <a name="see-also"></a>Vedere anche  
 [Cenni preliminari sulla grafica](../../../../docs/framework/winforms/advanced/graphics-overview-windows-forms.md)  
 [Informazioni sul codice gestito GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
 [Uso di classi grafiche gestite](../../../../docs/framework/winforms/advanced/using-managed-graphics-classes.md)
