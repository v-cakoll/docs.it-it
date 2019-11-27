---
title: Oggetto My.Resources
ms.date: 07/20/2015
f1_keywords:
- My.Resources
- My.Resources.MyResources.ResourceManager
- My.Resources.MyResources.Culture
helpviewer_keywords:
- My.Resources object
ms.assetid: 34c3f2dc-7b87-432c-9d5f-17ea666bb266
ms.openlocfilehash: 7f5d81194123ad2151a494a3cb79aa1955e0fdad
ms.sourcegitcommit: 17ee6605e01ef32506f8fdc686954244ba6911de
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 11/22/2019
ms.locfileid: "74350333"
---
# <a name="myresources-object"></a>Oggetto My.Resources
Fornisce le proprietà e le classi per l'accesso alle risorse dell'applicazione.  
  
## <a name="remarks"></a>Osservazioni  
 L'oggetto `My.Resources` fornisce l'accesso alle risorse dell'applicazione e consente di recuperare dinamicamente le risorse per l'applicazione. Per ulteriori informazioni, vedere [gestione delle risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 L'oggetto `My.Resources` espone solo le risorse globali. Non fornisce l'accesso ai file di risorse associati ai moduli. È necessario accedere alle risorse del modulo dal form.  
  
 È possibile accedere ai file di risorse specifici delle impostazioni cultura dell'applicazione dall'oggetto `My.Resources`. Per impostazione predefinita, l'oggetto `My.Resources` Cerca le risorse dal file di risorse che corrisponde alle impostazioni cultura nella proprietà <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A>. Tuttavia, è possibile eseguire l'override di questo comportamento e specificare impostazioni cultura specifiche da usare per le risorse. Per altre informazioni, vedere [Risorse nelle applicazioni desktop](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà dell'oggetto `My.Resources` forniscono l'accesso in sola lettura alle risorse dell'applicazione. Per aggiungere o rimuovere risorse, utilizzare **Progettazione progetti**. È possibile accedere alle risorse aggiunte tramite la **finestra di progettazione progetti** usando `My.Resources.`*resourceName*.  
  
 È anche possibile aggiungere o rimuovere file di risorse selezionando il progetto in **Esplora soluzioni** e facendo clic su **Aggiungi nuovo elemento** o **Aggiungi elemento esistente** dal menu **progetto** . È possibile accedere alle risorse aggiunte in questo modo usando `My.Resources.`*resourceFileName*`.`*resourceName*.  
  
 Ogni risorsa ha un nome, una categoria e un valore e queste impostazioni delle risorse determinano il modo in cui la proprietà per accedere alla risorsa viene visualizzata nell'oggetto `My.Resources`. Per le risorse aggiunte in **Progettazione progetti**:  
  
- Il nome determina il nome della proprietà.  
  
- I dati della risorsa corrispondono al valore della proprietà.  
  
- La categoria determina il tipo della proprietà:  
  
|Category|Tipo di dati della proprietà|  
|---|---|  
|**Stringhe**|[String](../../../visual-basic/language-reference/data-types/string-data-type.md)|  
|**Immagini**|<xref:System.Drawing.Bitmap>|  
|**Icone**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> La classe <xref:System.IO.UnmanagedMemoryStream> deriva dalla classe <xref:System.IO.Stream>, pertanto può essere utilizzata con i metodi che accettano flussi, ad esempio il metodo <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A>.|  
|**File**|-   [stringa](../../../visual-basic/language-reference/data-types/string-data-type.md) per i file di testo.<br />-   <xref:System.Drawing.Bitmap> per i file di immagine.<br />-   <xref:System.Drawing.Icon> per i file di icona.<br />-   <xref:System.IO.UnmanagedMemoryStream> per i file audio.|  
|**Altro**|Determinato dalle informazioni nella colonna di **tipo** della finestra di progettazione.|  
  
## <a name="classes"></a>Classi  
 L'oggetto `My.Resources` espone ogni file di risorse come classe con proprietà condivise. Il nome della classe corrisponde al nome del file di risorse. Come descritto nella sezione precedente, le risorse in un file di risorse vengono esposte come proprietà nella classe.  
  
## <a name="example"></a>Esempio  
 Questo esempio imposta il titolo di un form sulla risorsa di tipo stringa denominata `Form1Title` nel file di risorse dell'applicazione. Per il corretto funzionamento dell'esempio, l'applicazione deve avere una stringa denominata `Form1Title` nel file di risorse.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Esempio  
 Questo esempio imposta l'icona del form sull'icona denominata `Form1Icon` archiviata nel file di risorse dell'applicazione. Per il corretto funzionamento dell'esempio, l'applicazione deve avere un'icona denominata `Form1Icon` nel file di risorse.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Esempio  
 Questo esempio Mostra come impostare l'immagine di sfondo di un form sulla risorsa immagine denominata `Form1Background`, che si trova nel file di risorse dell'applicazione. Per il corretto funzionamento di questo esempio, l'applicazione deve avere una risorsa immagine denominata `Form1Background` nel file di risorse.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Questo esempio riproduce il suono archiviato come risorsa audio denominata `Form1Greeting` nel file di risorse dell'applicazione. Per il corretto funzionamento dell'esempio, è necessario che l'applicazione disponga di una risorsa audio denominata `Form1Greeting` nel file di risorse. Il metodo `My.Computer.Audio.Play` è disponibile solo per le applicazioni Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene recuperata la versione della lingua francese di una risorsa di stringa dell'applicazione. La risorsa è denominata `Message`. Per modificare le impostazioni cultura utilizzate dall'oggetto `My.Resources`, nell'esempio viene utilizzato <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A>.  
  
 Per il corretto funzionamento di questo esempio, l'applicazione deve avere una stringa denominata `Message` nel file di risorse e l'applicazione deve avere la versione in lingua francese del file di risorse, Resources.fr-FR. resx. Se per l'applicazione non è presente la versione in lingua francese del file di risorse, l'oggetto `My.Resource` recupera la risorsa dal file di risorse delle impostazioni cultura predefinite.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione delle risorse delle applicazioni (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Risorse nelle applicazioni desktop](../../../framework/resources/index.md)
