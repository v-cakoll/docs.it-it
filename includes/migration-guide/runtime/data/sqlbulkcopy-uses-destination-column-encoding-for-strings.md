---
ms.openlocfilehash: 1329a86db4227f75dfba7c50bbbdc2fc23099528
ms.sourcegitcommit: e02d17b2cf9c1258dadda4810a5e6072a0089aee
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 07/01/2020
ms.locfileid: "85620281"
---
### <a name="sqlbulkcopy-uses-destination-column-encoding-for-strings"></a><span data-ttu-id="07d37-101">SqlBulkCopy usa la codifica della colonna di destinazione per le stringhe</span><span class="sxs-lookup"><span data-stu-id="07d37-101">SqlBulkCopy uses destination column encoding for strings</span></span>

#### <a name="details"></a><span data-ttu-id="07d37-102">Dettagli</span><span class="sxs-lookup"><span data-stu-id="07d37-102">Details</span></span>

<span data-ttu-id="07d37-103">Nell'inserire i dati in una colonna, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> usa la codifica della colonna di destinazione anziché quella predefinita per i tipi <code>VARCHAR</code> e <code>CHAR</code>.</span><span class="sxs-lookup"><span data-stu-id="07d37-103">When inserting data into a column, <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> uses the encoding of the destination column rather than the default encoding for <code>VARCHAR</code> and <code>CHAR</code> types.</span></span> <span data-ttu-id="07d37-104">Questa modifica elimina la possibilità di danneggiamento dei dati causata dall'uso della codifica predefinita quando questa non viene usata dalla colonna di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07d37-104">This change eliminates the possibility of data corruption caused by using the default encoding when the destination column does not use the default encoding.</span></span> <span data-ttu-id="07d37-105">In rari casi, un'applicazione esistente può generare un'eccezione SqlException se la modifica nella codifica produce dati troppo grandi per rientrare nella colonna di destinazione.</span><span class="sxs-lookup"><span data-stu-id="07d37-105">In rare cases, an existing application may throw a SqlException exception if the change in encoding produces data that is too big to fit into the destination column.</span></span>

#### <a name="suggestion"></a><span data-ttu-id="07d37-106">Suggerimento</span><span class="sxs-lookup"><span data-stu-id="07d37-106">Suggestion</span></span>

<span data-ttu-id="07d37-107"><xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> non danneggerà più i dati a causa di differenze di codifica.</span><span class="sxs-lookup"><span data-stu-id="07d37-107">Expect that <xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=fullName> will no longer corrupt data due to encoding differences.</span></span> <span data-ttu-id="07d37-108">Se vengono copiate stringhe prossime al limite delle dimensioni della colonna di destinazione, può essere necessario pre-codificare i dati (copiarli per verificare che rientrino nella colonna di destinazione) o rilevare eccezioni <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>.</span><span class="sxs-lookup"><span data-stu-id="07d37-108">If strings near the destination column's size limit are being copied, it may be necessary to either pre-encode data (to be copied to check that the data will fit in the destination column) or catch <xref:System.Data.SqlClient.SqlException?displayProperty=fullName>s.</span></span>

| <span data-ttu-id="07d37-109">Nome</span><span class="sxs-lookup"><span data-stu-id="07d37-109">Name</span></span>    | <span data-ttu-id="07d37-110">Valore</span><span class="sxs-lookup"><span data-stu-id="07d37-110">Value</span></span>       |
|:--------|:------------|
| <span data-ttu-id="07d37-111">Scope</span><span class="sxs-lookup"><span data-stu-id="07d37-111">Scope</span></span>   |<span data-ttu-id="07d37-112">Microsoft Edge</span><span class="sxs-lookup"><span data-stu-id="07d37-112">Edge</span></span>|
|<span data-ttu-id="07d37-113">Version</span><span class="sxs-lookup"><span data-stu-id="07d37-113">Version</span></span>|<span data-ttu-id="07d37-114">4.5</span><span class="sxs-lookup"><span data-stu-id="07d37-114">4.5</span></span>|
|<span data-ttu-id="07d37-115">Type</span><span class="sxs-lookup"><span data-stu-id="07d37-115">Type</span></span>|<span data-ttu-id="07d37-116">Runtime</span><span class="sxs-lookup"><span data-stu-id="07d37-116">Runtime</span></span>

#### <a name="affected-apis"></a><span data-ttu-id="07d37-117">API interessate</span><span class="sxs-lookup"><span data-stu-id="07d37-117">Affected APIs</span></span>

-<xref:System.Data.SqlClient.SqlBulkCopy?displayProperty=nameWithType></li><li><xref:System.Data.SqlClient.SqlBulkCopy.%23ctor(System.Data.SqlClient.SqlConnection)></li></ul>|
