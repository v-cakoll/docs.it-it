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
ms.openlocfilehash: 25ce3fdd98560aba0918431bb77d6f3f23a04784
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57722464"
---
# <a name="metafiles-in-gdi"></a>Metafile in GDI+
[!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] fornisce il <xref:System.Drawing.Imaging.Metafile> classe in modo che è possibile registrare e visualizzare metafile. Un metafile, denominato anche immagine vettoriale, è un'immagine che viene archiviata come una sequenza di comandi e le impostazioni di disegno. I comandi e le impostazioni registrate un <xref:System.Drawing.Imaging.Metafile> oggetto può essere archiviato in memoria o salvato in un file o flusso.  
  
## <a name="metafile-formats"></a>Formati di metafile  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è possibile visualizzare metafile che sono stati archiviati nei formati seguenti:  
  
-   Windows Metafile (WMF)  
  
-   Enhanced Metafile (EMF)  
  
-   EMF+  
  
 [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] è in grado di registrare i metafile in formato EMF e EMF +, ma non nel formato di WMF.  
  
 EMF + è un'estensione di formato EMF che consenta [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record da archiviare. Esistono due varianti nel formato EMF +: EMF + solo ed EMF + Dual. EMF + solo metafile contengono solo [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record. È possibile visualizzare tale metafile per [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] ma non da [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)]. Metafile EMF + Dual contengono [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] e [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record. Ciascuna [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] record in un formato EMF + Dual metafile è associato a un'alternativa [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)] record. È possibile visualizzare tale metafile per [!INCLUDE[ndptecgdiplus](../../../../includes/ndptecgdiplus-md.md)] o tramite [!INCLUDE[ndptecgdi](../../../../includes/ndptecgdi-md.md)].  
  
 L'esempio seguente mostra un metafile salvato in precedenza come file. Viene visualizzato il metafile con relativo angolo superiore sinistro a (100, 100).  
  
 [!code-csharp[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/csharp/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/CS/Class1.cs#21)]
 [!code-vb[System.Drawing.ImagesBitmapsMetafiles#21](~/samples/snippets/visualbasic/VS_Snippets_Winforms/System.Drawing.ImagesBitmapsMetafiles/VB/Class1.vb#21)]  
  
## <a name="see-also"></a>Vedere anche
- [Immagini, bitmap e metafile](images-bitmaps-and-metafiles.md)
