---
title: 'Procedura: elencare i decodificatori installati'
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
- image codecs [Windows Forms], listing
- image decoders [Windows Forms], listing
ms.assetid: 11417191-8c95-40ca-8024-779e61706fb6
caps.latest.revision: "8"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.openlocfilehash: 17cbdebfa6cbb0cacacd923de4bd22125c812938
ms.sourcegitcommit: 4f3fef493080a43e70e951223894768d36ce430a
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/21/2017
---
# <a name="how-to-list-installed-decoders"></a>Procedura: elencare i decodificatori installati
È consigliabile elencare i decodificatori di immagini disponibili in un computer, per determinare se l'applicazione può leggere un formato di file di immagine specifico. Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A> metodi statici in modo che è possibile determinare quali immagini (decoder) sono disponibili. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageDecoders%2A>Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente genera l'elenco dei decodificatori installati e i relativi valori di proprietà.  
  
 [!code-csharp[UsingImageEncodersDecoders#2](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#2)]
 [!code-vb[UsingImageEncodersDecoders#2](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#2)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Form.  
  
-   Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Elencare i codificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-encoders.md)  
 [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
