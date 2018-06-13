---
title: Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: b2e51587209cb4df41ea1fd18ce5c2088ee07a2b
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
ms.locfileid: "33524501"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
Il <xref:System.Drawing> spazio dei nomi fornisce il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica di immagini. Utilizzando i codificatori in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile scrivere le immagini dalla memoria su disco. Utilizzando i decodificatori di immagini in [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)], è possibile caricare immagini dal disco nella memoria. Un decodificatore converte i dati in un <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto in un formato di file di disco designato. Un decodificatore converte i dati in un file su disco per il formato richiesto dal <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> oggetti.  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] dispone di codificatori e decodificatori che supportano i seguenti tipi di file incorporati:  
  
-   BMP  
  
-   GIF  
  
-   JPEG  
  
-   PNG  
  
-   TIFF  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] sono inoltre decodificatori incorporati che supportano i tipi di file seguenti:  
  
-   WMF  
  
-   EMF  
  
-   ICONA  
  
 Gli argomenti seguenti descrivono i codificatori e decodificatori in modo più dettagliato:  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Elencare i codificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 Viene descritto come elencare i codificatori disponibili in un computer.  
  
 [Procedura: Elencare i decodificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 Viene descritto come elencare i decodificatori disponibili in un computer.  
  
 [Procedura: Determinare i parametri supportati da un codificatore](../../../../docs/framework/winforms/advanced/how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Viene illustrato come elencare le <xref:System.Drawing.Imaging.EncoderParameters> supportati da un codificatore.  
  
 [Procedura: Convertire un'immagine BMP in un'immagine PNG](../../../../docs/framework/winforms/advanced/how-to-convert-a-bmp-image-to-a-png-image.md)  
 Viene descritto come salvare un'immagine in un formato di immagine diverso.  
  
 [Procedura: Impostare il livello di compressione JPEG](../../../../docs/framework/winforms/advanced/how-to-set-jpeg-compression-level.md)  
 Viene descritto come modificare il livello di qualità di un'immagine.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Informazioni sul codice gestito GDI+](../../../../docs/framework/winforms/advanced/about-gdi-managed-code.md)  
  
 [Immagini, bitmap e metafile](../../../../docs/framework/winforms/advanced/images-bitmaps-and-metafiles.md)
