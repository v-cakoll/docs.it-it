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
ms.openlocfilehash: 2b7c82c31d2e31ccbf573cf1dfa138af2d99ce29
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84372459"
---
# <a name="myresources-object"></a>Oggetto My.Resources
Fornisce le proprietà e le classi per l'accesso alle risorse dell'applicazione.  
  
## <a name="remarks"></a>Commenti  
 L' `My.Resources` oggetto fornisce l'accesso alle risorse dell'applicazione e consente di recuperare dinamicamente le risorse per l'applicazione. Per ulteriori informazioni, vedere [gestione delle risorse dell'applicazione (.NET)](/visualstudio/ide/managing-application-resources-dotnet).  
  
 L' `My.Resources` oggetto espone solo le risorse globali. Non fornisce l'accesso ai file di risorse associati ai moduli. È necessario accedere alle risorse del modulo dal form.  
  
 È possibile accedere ai file di risorse specifici delle impostazioni cultura dell'applicazione dall' `My.Resources` oggetto. Per impostazione predefinita, l' `My.Resources` oggetto cerca le risorse dal file di risorse che corrisponde alle impostazioni cultura nella <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.UICulture%2A> Proprietà. Tuttavia, è possibile eseguire l'override di questo comportamento e specificare impostazioni cultura specifiche da usare per le risorse. Per altre informazioni, vedere [Risorse nelle applicazioni desktop](../../../framework/resources/index.md).  
  
## <a name="properties"></a>Proprietà  
 Le proprietà dell' `My.Resources` oggetto forniscono l'accesso in sola lettura alle risorse dell'applicazione. Per aggiungere o rimuovere risorse, utilizzare **Progettazione progetti**. È possibile accedere alle risorse aggiunte tramite la **finestra di progettazione progetti** usando `My.Resources.` *resourceName*.  
  
 È anche possibile aggiungere o rimuovere file di risorse selezionando il progetto in **Esplora soluzioni** e facendo clic su **Aggiungi nuovo elemento** o **Aggiungi elemento esistente** dal menu **progetto** . È possibile accedere alle risorse aggiunte in questo modo utilizzando `My.Resources.` *resourceFileName* `.` *resourceName*.  
  
 Ogni risorsa ha un nome, una categoria e un valore e queste impostazioni delle risorse determinano il modo in cui la proprietà per accedere alla risorsa viene visualizzata nell' `My.Resources` oggetto. Per le risorse aggiunte in **Progettazione progetti**:  
  
- Il nome determina il nome della proprietà.  
  
- I dati della risorsa corrispondono al valore della proprietà.  
  
- La categoria determina il tipo della proprietà:  
  
|Categoria|Tipo di dati proprietà|  
|---|---|  
|**Stringhe**|[Stringa](../data-types/string-data-type.md)|  
|**Immagini**|<xref:System.Drawing.Bitmap>|  
|**Icone**|<xref:System.Drawing.Icon>|  
|**Audio**|<xref:System.IO.UnmanagedMemoryStream><br /><br /> La <xref:System.IO.UnmanagedMemoryStream> classe deriva dalla <xref:System.IO.Stream> classe, quindi può essere usata con metodi che accettano flussi, ad esempio il <xref:Microsoft.VisualBasic.Devices.Audio.Play%2A> metodo.|  
|**File**|-   [Stringa](../data-types/string-data-type.md) per i file di testo.<br />-   <xref:System.Drawing.Bitmap>per i file di immagine.<br />-   <xref:System.Drawing.Icon>per i file di icona.<br />-   <xref:System.IO.UnmanagedMemoryStream>per i file audio.|  
|**Altro**|Determinato dalle informazioni nella colonna di **tipo** della finestra di progettazione.|  
  
## <a name="classes"></a>Classi  
 L' `My.Resources` oggetto espone ogni file di risorse come classe con proprietà condivise. Il nome della classe corrisponde al nome del file di risorse. Come descritto nella sezione precedente, le risorse in un file di risorse vengono esposte come proprietà nella classe.  
  
## <a name="example"></a>Esempio  
 Questo esempio Mostra come impostare il titolo di un form sulla risorsa stringa denominata `Form1Title` nel file di risorse dell'applicazione. Per il corretto funzionamento dell'esempio, l'applicazione deve avere una stringa denominata `Form1Title` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#1](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#1)]  
  
## <a name="example"></a>Esempio  
 Questo esempio Mostra come impostare l'icona del form sull'icona denominata `Form1Icon` archiviata nel file di risorse dell'applicazione. Per il corretto funzionamento dell'esempio, l'applicazione deve avere un'icona denominata `Form1Icon` nel relativo file di risorse.  
  
 [!code-vb[VbVbalrMyResources#2](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#2)]  
  
## <a name="example"></a>Esempio  
 Questo esempio Mostra come impostare l'immagine di sfondo di un form sulla risorsa immagine denominata `Form1Background` , che si trova nel file di risorse dell'applicazione. Per il corretto funzionamento di questo esempio, l'applicazione deve avere una risorsa immagine denominata `Form1Background` nel file di risorse.  
  
 [!code-vb[VbVbalrMyResources#3](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#3)]  
  
## <a name="example"></a>Esempio  
 Questo esempio riproduce il suono archiviato come risorsa audio denominata `Form1Greeting` nel file di risorse dell'applicazione. Per il corretto funzionamento dell'esempio, l'applicazione deve avere una risorsa audio denominata `Form1Greeting` nel file di risorse. Il `My.Computer.Audio.Play` metodo è disponibile solo per le applicazioni Windows Forms.  
  
 [!code-vb[VbVbalrMyResources#4](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#4)]  
  
## <a name="example"></a>Esempio  
 In questo esempio viene recuperata la versione della lingua francese di una risorsa di stringa dell'applicazione. La risorsa è denominata `Message` . Per modificare le impostazioni cultura `My.Resources` utilizzate dall'oggetto, nell'esempio viene utilizzato <xref:Microsoft.VisualBasic.ApplicationServices.ApplicationBase.ChangeUICulture%2A> .  
  
 Per il corretto funzionamento di questo esempio, l'applicazione deve avere una stringa denominata `Message` nel relativo file di risorse e l'applicazione deve avere la versione in lingua francese del file di risorse, resources.fr-fr. resx. Se per l'applicazione non è presente la versione in lingua francese del file di risorse, l' `My.Resource` oggetto recupera la risorsa dal file di risorse delle impostazioni cultura predefinite.  
  
 [!code-vb[VbVbalrMyResources#10](~/samples/snippets/visualbasic/VS_Snippets_VBCSharp/VbVbalrMyResources/VB/Form1.vb#10)]  
  
## <a name="see-also"></a>Vedere anche

- [Gestione delle risorse delle applicazioni (.NET)](/visualstudio/ide/managing-application-resources-dotnet)
- [Risorse nelle applicazioni desktop](../../../framework/resources/index.md)
