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
ms.openlocfilehash: 59200941aa0f872a0bd99510bfaa8a8b878a9061
ms.sourcegitcommit: 2701302a99cafbe0d86d53d540eb0fa7e9b46b36
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/28/2019
ms.locfileid: "64648296"
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Procedura: Convertire un'immagine BMP in un'immagine PNG
Spesso può essere opportuno convertire un formato di file immagine in un altro. È possibile eseguire questa conversione chiamando il metodo <xref:System.Drawing.Image.Save%2A> della classe <xref:System.Drawing.Image> e specificando l'oggetto <xref:System.Drawing.Imaging.ImageFormat> per il formato di file immagine desiderato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene caricata un'immagine BMP da un tipo e quindi salvata nel formato PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
- Applicazione Windows Forms.  
  
- Un riferimento allo spazio dei nomi `System.Drawing.Imaging`.  
  
## <a name="see-also"></a>Vedere anche

- [Procedura: Elencare i codificatori installati](how-to-list-installed-encoders.md)
- [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)
- [Tipi di bitmap](types-of-bitmaps.md)
