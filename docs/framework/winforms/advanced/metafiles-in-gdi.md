---
title: Metafile in GDI+
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- images [Windows Forms], metafiles
- GDI+, metafiles
- metafiles
ms.assetid: 51da872c-c783-440f-8bf6-1e580a966c31
ms.openlocfilehash: df54289722cf12bad840722c6eafdaa43279a5dc
ms.sourcegitcommit: b1cfd260928d464d91e20121f9bdba7611c94d71
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/02/2019
ms.locfileid: "67504580"
---
# <a name="metafiles-in-gdi"></a>Metafile in GDI+
GDI+ è disponibile il <xref:System.Drawing.Imaging.Metafile> classe in modo che è possibile registrare e visualizzare metafile. Un metafile, denominato anche immagine vettoriale, è un'immagine che viene archiviata come una sequenza di comandi e le impostazioni di disegno. I comandi e le impostazioni registrate un <xref:System.Drawing.Imaging.Metafile> oggetto può essere archiviato in memoria o salvato in un file o flusso.  
  
## <a name="metafile-formats"></a>Formati di metafile  
 GDI+ possono visualizzare metafile che sono stati archiviati nei formati seguenti:  
  
- Windows Metafile (WMF)  
  
- Enhanced Metafile (EMF)  
  
- EMF+  
  
 GDI+ in grado di registrare i metafile in formato EMF e EMF +, ma non nel formato di WMF.  
  
 EMF + è un'estensione EMF che consente i record GDI+ da archiviare. Esistono due varianti nel formato EMF +: EMF + solo ed EMF + Dual. Metafile EMF + solo contengono solo record GDI+. Tali metafile visualizzabili mediante GDI+, ma non GDI. Metafile EMF + Dual contengono record GDI+ e GDI. Ogni record GDI+ in un metafile EMF + Dual viene abbinato a un record GDI alternativo. Tali metafile possono essere visualizzati mediante GDI+ o GDI.  
  
 L'esempio seguente mostra un metafile salvato in precedenza come file. Viene visualizzato il metafile con relativo angolo superiore sinistro a (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche

- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
