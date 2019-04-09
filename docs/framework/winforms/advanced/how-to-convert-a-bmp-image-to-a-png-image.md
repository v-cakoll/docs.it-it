---
title: "Procedura: Convertire un'immagine BMP in un'immagine PNG"
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
ms.openlocfilehash: 3072c07781a8e8e57b64b48e5b4c304c2a0a0efb
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59217016"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Procedura: Convertire un'immagine BMP in un'immagine PNG
Spesso può essere opportuno convertire un formato di file immagine in un altro. È possibile eseguire questa conversione chiamando il metodo <xref:System.Drawing.Image.Save%2A> della classe <xref:System.Drawing.Image> e specificando l'oggetto <xref:System.Drawing.Imaging.ImageFormat> per il formato di file immagine desiderato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene caricata un'immagine BMP da un tipo e quindi salvata nel formato PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Forms.  
  
-   Un riferimento allo spazio dei nomi `System.Drawing.Imaging`.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Elencare i codificatori installati](how-to-list-installed-encoders.md)
- [Utilizzo di codificatori e decodificatori di immagini nel codice gestito GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)
- [Tipi di bitmap](types-of-bitmaps.md)
