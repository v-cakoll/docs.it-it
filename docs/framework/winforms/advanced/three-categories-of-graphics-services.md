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
ms.openlocfilehash: ccbd5e236b47d1d870c9b77cfa2b3880619cf3cd
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59083595"
---
# <a name="three-categories-of-graphics-services"></a>Tre categorie di servizi grafici
Le offerte di grafica in Windows Form possono essere suddivise in tre categorie generali seguenti:  
  
-   Grafica vettoriale bidimensionale (2D)  
  
-   Creazione di immagini  
  
-   Opzioni tipografiche  
  
## <a name="2-d-vector-graphics"></a>Grafica vettoriale 2D  
 Grafica vettoriale bidimensionale è tipi primitivi; ad esempio linee, curve e le cifre; dal set di punti su un sistema di coordinate specificati. Ad esempio, una linea retta specificata dal relativo due endpoint, e un rettangolo specificato da un punto fornisce la posizione dell'angolo superiore sinistro e una coppia di numeri che ne indicano la larghezza e altezza. Viene specificato un percorso semplice da una matrice di punti connessi da linee rette. Una spline di Bézier è una sofisticata curva specificata da quattro punti di controllo.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce classi e strutture che archiviano informazioni sulle primitive autonomamente, le classi che archiviano informazioni sul modo in cui verranno disegnate le primitive e le classi che eseguono effettivamente il disegno. Ad esempio, il <xref:System.Drawing.Rectangle> struttura consente di archiviare la posizione e dimensione di un rettangolo; la <xref:System.Drawing.Pen> classe archivia le informazioni sul colore della linea di spessore della linea e stile di linea e il <xref:System.Drawing.Graphics> classe include metodi per il disegno di linee, rettangoli, percorsi, e altre figure. Esistono anche diversi <xref:System.Drawing.Brush> le classi che contengono informazioni sulla modalità chiuso figure e i percorsi verranno compilati con i colori o i modelli.  
  
 È possibile registrare un'immagine di vector, ovvero una sequenza di comandi di grafica, in un metafile. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce il <xref:System.Drawing.Imaging.Metafile> classe per la registrazione, la visualizzazione e salvataggio del metafile. Con il <xref:System.Drawing.Imaging.MetafileHeader> e <xref:System.Drawing.Imaging.MetaHeader> classi, è possibile esaminare i dati archiviati in un'intestazione di metafile.  
  
## <a name="imaging"></a>Creazione di immagini  
 Determinati tipi di immagini sono difficili o impossibili da visualizzare con le tecniche di grafica vettoriale. Ad esempio, le immagini sui pulsanti della barra degli strumenti e le immagini che vengono visualizzati come icone sono difficili da specificare come le raccolte di linee e curve. Una fotografia digitale ad alta risoluzione di uno stadio affollato è ancora più difficile da creare con le tecniche di vettore. Le immagini di questo tipo vengono archiviate come bitmap, che sono matrici dei numeri che rappresentano i colori dei punti di singole sullo schermo. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce il <xref:System.Drawing.Bitmap> classe per la visualizzazione, modifica e salvataggio di bitmap.  
  
## <a name="typography"></a>Opzioni tipografiche  
 Funzionalità tipografiche è la visualizzazione del testo in un'ampia gamma di tipi di carattere, dimensioni e stili. [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce supporto completo per questa attività complessa. Una delle nuove funzionalità di [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è anti-aliasing dei subpixel, che fornisce il testo viene eseguito il rendering su uno schermo LCD un aspetto più uniforme.  
  
 Inoltre, Windows Form offre la possibilità di creare testo con [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] funzionalità della relativa <xref:System.Windows.Forms.TextRenderer> classe.  
  
## <a name="see-also"></a>Vedere anche

- [Panoramica sulla grafica](graphics-overview-windows-forms.md)
- [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)
- [Utilizzo di classi grafiche gestite](using-managed-graphics-classes.md)
