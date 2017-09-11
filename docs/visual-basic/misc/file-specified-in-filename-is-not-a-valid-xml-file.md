---
title: "File specificato nel nome file non è un file XML valido | Documenti di Microsoft"
ms.date: 2015-07-20
ms.prod: .net
ms.technology:
- devlang-visual-basic
ms.topic: article
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
caps.latest.revision: 12
author: dotnet-bot
ms.author: dotnetcontent
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 9f5b8ebb69c9206ff90b05e748c64d29d82f7a16
ms.openlocfilehash: 8b46b9d896f0dce401992e8a20e040b85091ba5d
ms.contentlocale: it-it
ms.lasthandoff: 04/12/2017

---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="e760a-102">Il file specificato in FileName non è un file XML valido</span><span class="sxs-lookup"><span data-stu-id="e760a-102">File specified in FileName is not a valid XML file</span></span>
<span data-ttu-id="e760a-103">Il nome file fornito non è un file XML valido.</span><span class="sxs-lookup"><span data-stu-id="e760a-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="e760a-104">Per specificare la struttura e il contenuto consentito di un documento XML, è possibile usare una definizione DTD (Document Type Definition), uno schema XDR (XML-Data Reduced) o uno schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="e760a-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="e760a-105">Gli schemi XSD sono il modo migliore per specificare le grammatiche XML nel [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span><span class="sxs-lookup"><span data-stu-id="e760a-105">XSD schemas are the preferred way to specify XML grammars in the [!INCLUDE[dnprdnshort](../../csharp/getting-started/includes/dnprdnshort_md.md)].</span></span>  
  
> [!NOTE]
>  <span data-ttu-id="e760a-106">Nelle precedenti versioni di Visual Studio, **Progettazione XML** è la finestra di progettazione per i dataset tipizzati e lo schema XML.</span><span class="sxs-lookup"><span data-stu-id="e760a-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="e760a-107">È ancora possibile usare **Progettazione XML** per creare e modificare i file di schema XML.</span><span class="sxs-lookup"><span data-stu-id="e760a-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="e760a-108">Tuttavia, in [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], la finestra di progettazione per la creazione e modifica di dataset tipizzati il **Progettazione Dataset**.</span><span class="sxs-lookup"><span data-stu-id="e760a-108">However, in [!INCLUDE[vs_current_long](../../csharp/misc/includes/vs_current_long_md.md)], the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="e760a-109">Per ulteriori informazioni, vedere [creazione e modifica di dataset tipizzati](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span><span class="sxs-lookup"><span data-stu-id="e760a-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/visualstudio/data-tools/creating-and-editing-typed-datasets).</span></span>  
  
## <a name="to-correct-this-error"></a><span data-ttu-id="e760a-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="e760a-110">To correct this error</span></span>  
  
-   <span data-ttu-id="e760a-111">Verificare che il nome file fornito sia corretto.</span><span class="sxs-lookup"><span data-stu-id="e760a-111">Check that you are supplying the correct file name.</span></span>  
  
-   <span data-ttu-id="e760a-112">Accertarsi che il file specificato contenga XML valido, caricando il file XML che si vuole verificare in **Progettazione XML**.</span><span class="sxs-lookup"><span data-stu-id="e760a-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="e760a-113">Scegliere **Convalida dati XML** dal menu **XML**.</span><span class="sxs-lookup"><span data-stu-id="e760a-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="e760a-114">Gli errori sono visualizzati nell' **Elenco attività**.</span><span class="sxs-lookup"><span data-stu-id="e760a-114">Errors are displayed in the **Task List**.</span></span>  
  
-   <span data-ttu-id="e760a-115">Se il file XML ha uno schema XML associato, verificare che gli elementi appaiano nella struttura definita e che il contenuto dei singoli elementi sia conforme ai tipi di dati dichiarati specificati nello schema.</span><span class="sxs-lookup"><span data-stu-id="e760a-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="e760a-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="e760a-116">See Also</span></span>  
 <span data-ttu-id="e760a-117"><xref:System.Xml></xref:System.Xml></span><span class="sxs-lookup"><span data-stu-id="e760a-117"><xref:System.Xml></span></span>   
<span data-ttu-id="e760a-118"> [Procedura: analizzare percorsi di file](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span><span class="sxs-lookup"><span data-stu-id="e760a-118"> [How to: Parse File Paths](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)</span></span>
