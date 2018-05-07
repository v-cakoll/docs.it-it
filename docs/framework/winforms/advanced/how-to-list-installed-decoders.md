---
title: 'Procedura: elencare i decodificatori installati'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
ms.openlocfilehash: 8a9dce0e4fd833bbda7bec5d35d26ef09a1fa761
ms.sourcegitcommit: 3d5d33f384eeba41b2dff79d096f47ccc8d8f03d
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/04/2018
---
# <a name="how-to-list-installed-decoders"></a>Procedura: elencare i decodificatori installati
È consigliabile elencare i decodificatori di immagini disponibili in un computer, per determinare se l'applicazione può leggere un formato di file di immagine specifico. Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> metodi statici in modo che è possibile determinare quali immagini (decoder) sono disponibili. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente genera l'elenco dei decodificatori installati e i relativi valori di proprietà.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Forms.  
  
-   Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Elencare i codificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
