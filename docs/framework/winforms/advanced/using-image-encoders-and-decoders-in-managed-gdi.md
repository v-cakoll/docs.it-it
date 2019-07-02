---
title: Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
ms.date: 03/30/2017
helpviewer_keywords:
- image encoders [Windows Forms], using
- image decoders [Windows Forms], using
ms.assetid: 0e838ea1-4e7e-4334-b882-ab25df607b8b
ms.openlocfilehash: 8cd66f3ce3da462867da9e23c38b3f6d877c058c
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67505083"
---
# <a name="using-image-encoders-and-decoders-in-managed-gdi"></a>Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+
Il <xref:System.Drawing> spazio dei nomi fornisce le <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> classi per l'archiviazione e la modifica delle immagini. Usando codificatori di immagini in GDI+, è possibile scrivere le immagini dalla memoria su disco. Tramite i decodificatori di immagini in GDI+, è possibile caricare immagini dal disco in memoria. Un codificatore converte i dati in un' <xref:System.Drawing.Image> o <xref:System.Drawing.Bitmap> oggetto in un formato di file di disco designato. Un decodificatore converte i dati in un file di disco per il formato richiesto per il <xref:System.Drawing.Image> e <xref:System.Drawing.Bitmap> oggetti.  
  
 GDI+ è incorporati codificatori e decodificatori di immagini che supportano i tipi di file seguenti:  
  
- BMP  
  
- GIF  
  
- JPEG  
  
- PNG  
  
- TIFF  
  
 GDI+ dispone anche di decodificatori di immagini predefinite che supportano i tipi di file seguenti:  
  
- WMF  
  
- EMF  
  
- ICON  
  
 Gli argomenti seguenti descrivono i codificatori e decodificatori di immagini in modo più dettagliato:  
  
## <a name="in-this-section"></a>In questa sezione  
 [Procedura: Elencare i codificatori installati](how-to-list-installed-encoders.md)  
 Descrive come elencare i codificatori disponibili in un computer.  
  
 [Procedura: Elencare i decodificatori installati](how-to-list-installed-decoders.md)  
 Viene descritto come elencare i decodificatori disponibili in un computer.  
  
 [Procedura: Determinare i parametri supportati da un codificatore](how-to-determine-the-parameters-supported-by-an-encoder.md)  
 Viene illustrato come elencare le <xref:System.Drawing.Imaging.EncoderParameters> supportati da un codificatore.  
  
 [Procedura: Convertire un'immagine BMP in un'immagine PNG](how-to-convert-a-bmp-image-to-a-png-image.md)  
 Viene descritto come salvare un'immagine in un formato di immagine diversi.  
  
 [Procedura: Impostare il livello di compressione JPEG](how-to-set-jpeg-compression-level.md)  
 Viene descritto come modificare il livello di qualità di un'immagine.  
  
## <a name="reference"></a>Riferimenti  
 <xref:System.Drawing.Image>  
  
 <xref:System.Drawing.Bitmap>  
  
 <xref:System.Drawing.Imaging.ImageCodecInfo>  
  
 <xref:System.Drawing.Imaging.EncoderParameter>  
  
 <xref:System.Drawing.Imaging.Encoder>  
  
## <a name="related-sections"></a>Sezioni correlate  
 [Informazioni sul codice gestito GDI+](about-gdi-managed-code.md)  
  
 [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
