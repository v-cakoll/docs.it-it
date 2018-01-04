---
title: 'Procedura: elencare i codificatori installati'
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
- image encoders [Windows Forms], listing
ms.assetid: 49e8e4e9-7a67-42d9-86bf-08821cdc282e
caps.latest.revision: "9"
author: dotnet-bot
ms.author: dotnetcontent
manager: wpickett
ms.workload: dotnet
ms.openlocfilehash: ec3ce7d2d933226162664826764c818eacf97afc
ms.sourcegitcommit: 16186c34a957fdd52e5db7294f291f7530ac9d24
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 12/22/2017
---
# <a name="how-to-list-installed-encoders"></a>Procedura: elencare i codificatori installati
È consigliabile elencare i codificatori disponibili in un computer, per determinare se l'applicazione è possibile salvare in un formato di file di immagine specifico. Il <xref:System.Drawing.Imaging.ImageCodecInfo> classe fornisce il <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A> metodi statici in modo che è possibile determinare quali codificatori sono disponibili. <xref:System.Drawing.Imaging.ImageCodecInfo.GetImageEncoders%2A>Restituisce una matrice di <xref:System.Drawing.Imaging.ImageCodecInfo> oggetti.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente genera l'elenco di codificatori installati e i relativi valori di proprietà.  
  
 [!code-csharp[UsingImageEncodersDecoders#1](../../../../samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#1)]
 [!code-vb[UsingImageEncodersDecoders#1](../../../../samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#1)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Forms.  
  
-   Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche  
 [Procedura: Elencare i decodificatori installati](../../../../docs/framework/winforms/advanced/how-to-list-installed-decoders.md)  
 [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](../../../../docs/framework/winforms/advanced/using-image-encoders-and-decoders-in-managed-gdi.md)
