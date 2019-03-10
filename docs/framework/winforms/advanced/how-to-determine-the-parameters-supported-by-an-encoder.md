---
title: 'Procedura: Determinare i parametri supportati da un codificatore'
ms.date: 03/30/2017
dev_langs:
- csharp
- vb
helpviewer_keywords:
- encoder parameters [Windows Forms], determining supported
ms.assetid: f47ae459-e3ce-4d41-a140-2f6c6aea3f44
ms.openlocfilehash: f5af00833c8d8373444b475673709d902598d9d0
ms.sourcegitcommit: 160a88c8087b0e63606e6e35f9bd57fa5f69c168
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 03/09/2019
ms.locfileid: "57719702"
---
# <a name="how-to-determine-the-parameters-supported-by-an-encoder"></a>Procedura: Determinare i parametri supportati da un codificatore
È possibile modificare i parametri dell'immagine, ad esempio a livello di qualità e la compressione, ma è necessario conoscere quali parametri sono supportati da un codificatore di immagini specificato. Il <xref:System.Drawing.Image> classe fornisce il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo in modo da poter determinare quali parametri dell'immagine sono supportate per un codificatore particolare. Specificare il codificatore con un GUID. Il <xref:System.Drawing.Image.GetEncoderParameterList%2A> metodo restituisce una matrice di <xref:System.Drawing.Imaging.EncoderParameter> oggetti.  
  
## <a name="example"></a>Esempio  
 Esempio di codice seguente restituisce i parametri supportati per il codificatore JPEG. Usare l'elenco delle categorie di parametro e i GUID associati nel <xref:System.Drawing.Imaging.Encoder> Cenni preliminari sulla classe per determinare la categoria per ogni parametro.  
  
 [!code-csharp[UsingImageEncodersDecoders#3](~/samples/snippets/csharp/VS_Snippets_Winforms/UsingImageEncodersDecoders/CS/Form1.cs#3)]
 [!code-vb[UsingImageEncodersDecoders#3](~/samples/snippets/visualbasic/VS_Snippets_Winforms/UsingImageEncodersDecoders/VB/Form1.vb#3)]  
  
## <a name="compiling-the-code"></a>Compilazione del codice  
 L'esempio presenta i requisiti seguenti:  
  
-   Applicazione Windows Forms.  
  
-   Oggetto <xref:System.Windows.Forms.PaintEventArgs>, ovvero un parametro di <xref:System.Windows.Forms.PaintEventHandler>.  
  
## <a name="see-also"></a>Vedere anche
- [Procedura: Elencare i codificatori installati](how-to-list-installed-encoders.md)
- [Tipi di bitmap](types-of-bitmaps.md)
- [Uso di codificatori e decodificatori di immagini nel codice gestito GDI+](using-image-encoders-and-decoders-in-managed-gdi.md)
