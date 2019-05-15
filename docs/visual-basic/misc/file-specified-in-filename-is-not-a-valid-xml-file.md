---
title: Il file specificato in FileName non è un file XML valido
ms.date: 07/20/2015
ms.assetid: c4c30bf3-e0ad-4bc8-89e0-2c3e49e9793b
ms.openlocfilehash: 5a54e5e7e7c75bb7d766b1bbda10f401fa8b99af
ms.sourcegitcommit: 8699383914c24a0df033393f55db3369db728a7b
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 05/15/2019
ms.locfileid: "65640842"
---
# <a name="file-specified-in-filename-is-not-a-valid-xml-file"></a><span data-ttu-id="94e05-102">Il file specificato in FileName non è un file XML valido</span><span class="sxs-lookup"><span data-stu-id="94e05-102">File specified in FileName is not a valid XML file</span></span>

<span data-ttu-id="94e05-103">Il nome file fornito non è un file XML valido.</span><span class="sxs-lookup"><span data-stu-id="94e05-103">The file name that you supplied is not a valid XML file.</span></span> <span data-ttu-id="94e05-104">Per specificare la struttura e il contenuto consentito di un documento XML, è possibile usare una definizione DTD (Document Type Definition), uno schema XDR (XML-Data Reduced) o uno schema XSD (XML Schema Definition Language).</span><span class="sxs-lookup"><span data-stu-id="94e05-104">To specify the allowed structure and content of an XML document, you can use a Document Type Definition (DTD), a Microsoft XML-Data Reduced (XDR) schema, or an XML Schema definition language (XSD) schema.</span></span> <span data-ttu-id="94e05-105">Schemi XSD rappresentano modo migliore per specificare le grammatiche XML in .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="94e05-105">XSD schemas are the preferred way to specify XML grammars in the .NET Framework.</span></span>

> [!NOTE]
> <span data-ttu-id="94e05-106">Nelle precedenti versioni di Visual Studio, **Progettazione XML** è la finestra di progettazione per i dataset tipizzati e lo schema XML.</span><span class="sxs-lookup"><span data-stu-id="94e05-106">In some earlier versions of Visual Studio, the **XML Designer** is the designer for typed datasets and XML schema.</span></span> <span data-ttu-id="94e05-107">È ancora possibile usare **Progettazione XML** per creare e modificare i file di schema XML.</span><span class="sxs-lookup"><span data-stu-id="94e05-107">The **XML Designer** can still be used to create and edit XML schema files.</span></span> <span data-ttu-id="94e05-108">Tuttavia, in Visual Studio 2012, la finestra di progettazione per la creazione e modifica di dataset tipizzati è il **Progettazione Dataset**.</span><span class="sxs-lookup"><span data-stu-id="94e05-108">However, in Visual Studio 2012, the designer for creating and editing typed datasets is the **Dataset Designer**.</span></span> <span data-ttu-id="94e05-109">Per altre informazioni, vedere [creazione e modifica di dataset tipizzati](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span><span class="sxs-lookup"><span data-stu-id="94e05-109">For more information, see [Creating and Editing Typed Datasets](https://docs.microsoft.com/previous-versions/visualstudio/visual-studio-2013/314t4see(v=vs.120)).</span></span>

## <a name="to-correct-this-error"></a><span data-ttu-id="94e05-110">Per correggere l'errore</span><span class="sxs-lookup"><span data-stu-id="94e05-110">To correct this error</span></span>

- <span data-ttu-id="94e05-111">Verificare che il nome file fornito sia corretto.</span><span class="sxs-lookup"><span data-stu-id="94e05-111">Check that you are supplying the correct file name.</span></span>

- <span data-ttu-id="94e05-112">Accertarsi che il file specificato contenga XML valido, caricando il file XML che si vuole verificare in **Progettazione XML**.</span><span class="sxs-lookup"><span data-stu-id="94e05-112">Check that the specified file contains valid XML by loading the XML file that you want to check into the **XML Designer**.</span></span> <span data-ttu-id="94e05-113">Scegliere **Convalida dati XML** dal menu **XML**.</span><span class="sxs-lookup"><span data-stu-id="94e05-113">From the **XML** menu, click **Validate XML**.</span></span> <span data-ttu-id="94e05-114">Gli errori sono visualizzati nell' **Elenco attività**.</span><span class="sxs-lookup"><span data-stu-id="94e05-114">Errors are displayed in the **Task List**.</span></span>

- <span data-ttu-id="94e05-115">Se il file XML ha uno schema XML associato, verificare che gli elementi appaiano nella struttura definita e che il contenuto dei singoli elementi sia conforme ai tipi di dati dichiarati specificati nello schema.</span><span class="sxs-lookup"><span data-stu-id="94e05-115">If the XML file has an associated XML Schema, check that the elements appear in the defined structure and that the content of the individual elements conforms to the declared data types specified in the schema.</span></span>

## <a name="see-also"></a><span data-ttu-id="94e05-116">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="94e05-116">See also</span></span>

- <xref:System.Xml>
- [<span data-ttu-id="94e05-117">Procedura: Analizzare percorsi di file</span><span class="sxs-lookup"><span data-stu-id="94e05-117">How to: Parse File Paths</span></span>](../../visual-basic/developing-apps/programming/drives-directories-files/how-to-parse-file-paths.md)
