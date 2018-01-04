---
title: 'Procedura: convertire un''immagine BMP in un''immagine PNG'
ms.custom: 
ms.date: 03/30/2017
ms.prod: .net-framework
ms.reviewer: 
ms.suite: 
ms.technology: dotnet-winforms
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- csharp
- vb
helpviewer_keywords:
- BMP images [Windows Forms], converting to PNG
- image formats [Windows Forms], converting between
ms.assetid: 9d4a692d-73ac-4ce3-9e05-9ec321e8fbd6
caps.latest.revision: "10"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: 2ee2669c41f4ee558d9457cee7df0ae8425cf065
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-convert-a-bmp-image-to-a-png-image"></a>Procedura: convertire un'immagine BMP in un'immagine PNG
Spesso può essere opportuno convertire un formato di file immagine in un altro. È possibile eseguire questa conversione chiamando il metodo <xref:System.Drawing.Image.Save%2A> della classe <xref:System.Drawing.Image> e specificando l'oggetto <xref:System.Drawing.Imaging.ImageFormat> per il formato di file immagine desiderato.  
  
## <a name="example"></a>Esempio  
 Nell'esempio seguente viene caricata un'immagine BMP da un tipo e quindi salvata nel formato PNG.  
  
 [!code-csharp[UsingImageEncodersDecoders#4](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#4)]
 [!code-vb[UsingImageEncodersDecoders#4](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#4)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Form.  
  
-   Un riferimento allo spazio dei nomi `System.Drawing.Imaging`.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Elencare i codificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)  
 [Tipi di bitmap](../../../../docs/framework/winforms/advanced/types-of-bitmaps.md)
