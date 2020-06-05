---
title: Il file specificato in FileName non è un file XML valido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: a84042490935e3e7e5a6de2a802d9effd5b4d3d4
ms.sourcegitcommit: f8c270376ed905f6a8896ce0fe25b4f4b38ff498
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 06/04/2020
ms.locfileid: "84358348"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="4b0c3-102">Il file specificato in FileName non è un file XML valido</span><span class="sxs-lookup"><span data-stu-id="4b0c3-102">File specified in FileName is not a valid XML file</span></span>

<span data-ttu-id="4b0c3-103">Il nome file fornito non è un file XML valido.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="4b0c3-104">Per specificare la struttura e il contenuto consentito di un documento XML, è possibile usare una definizione DTD (Document Type Definition), uno schema XDR (XML-Data Reduced) o uno schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="4b0c3-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="4b0c3-105">Gli schemi XSD rappresentano il modo migliore per specificare le grammatiche XML nella .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-105">XSD schemas are the preferred way to specify XML grammars in the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="4b0c3-106">Nelle precedenti versioni di Visual Studio, **Progettazione XML** è la finestra di progettazione per i dataset tipizzati e lo schema XML.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="4b0c3-107">È ancora possibile usare **Progettazione XML** per creare e modificare i file di schema XML.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="4b0c3-108">Tuttavia, in Visual Studio 2012, la finestra di progettazione per la creazione e la modifica di DataSet tipizzati è la **Progettazione DataSet**.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="4b0c3-109">Per altre informazioni, vedere [creazione e modifica di DataSet tipizzati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="4b0c3-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="4b0c3-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="4b0c3-110">To correct this error</span></span>

- <span data-ttu-id="4b0c3-111">Verificare che il nome file fornito sia corretto.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-111">Check that you are supplying the correct file name.</span></span>

- <span data-ttu-id="4b0c3-112">Accertarsi che il file specificato contenga XML valido, caricando il file XML che si vuole verificare in **Progettazione XML**.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="4b0c3-113">Scegliere **Convalida dati XML** dal menu **XML**.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="4b0c3-114">Gli errori sono visualizzati nell' **Elenco attività**.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-114">Errors are displayed in the **Task List**.</span></span>

- <span data-ttu-id="4b0c3-115">Se il file XML ha uno schema XML associato, verificare che gli elementi appaiano nella struttura definita e che il contenuto dei singoli elementi sia conforme ai tipi di dati dichiarati specificati nello schema.</span><span class="sxs-lookup"><span data-stu-id="4b0c3-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="4b0c3-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="4b0c3-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="4b0c3-117">Procedura: Analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="4b0c3-117">How to: Parse File Paths</span></span>](../developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
