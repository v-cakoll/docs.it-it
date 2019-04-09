---
title: Metodi System.String
ms.date: 03/30/2017
ms.assetid: ce307f14-87e6-4816-8694-8a4147f6b784
ms.openlocfilehash: 3a7b45f27441d889524f5055eb5c6a3b06937bd3
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59160498"
---
# <a name="systemstring-methods"></a><span data-ttu-id="24da9-102">Metodi System.String</span><span class="sxs-lookup"><span data-stu-id="24da9-102">System.String Methods</span></span>
[!INCLUDE[vbtecdlinq](../../../../../../includes/vbtecdlinq-md.md)] <span data-ttu-id="24da9-103">non supporta quanto segue <xref:System.String> metodi.</span><span class="sxs-lookup"><span data-stu-id="24da9-103">does not support the following <xref:System.String> methods.</span></span>  
  
## <a name="unsupported-systemstring-methods-in-general"></a><span data-ttu-id="24da9-104">Metodi System.String non supportati in generale</span><span class="sxs-lookup"><span data-stu-id="24da9-104">Unsupported System.String Methods in General</span></span>  
 <span data-ttu-id="24da9-105">Metodi <xref:System.String> non supportati in generale:</span><span class="sxs-lookup"><span data-stu-id="24da9-105">Unsupported <xref:System.String> methods in general:</span></span>  
  
-   <span data-ttu-id="24da9-106">Overload con il supporto delle impostazioni cultura (metodi che accettano un `CultureInfo`  /  `StringComparison`  /  `IFormatProvider`).</span><span class="sxs-lookup"><span data-stu-id="24da9-106">Culture-aware overloads (methods that take a `CultureInfo` / `StringComparison` / `IFormatProvider`).</span></span>  
  
-   <span data-ttu-id="24da9-107">Metodi che accettano o producono una matrice `char`.</span><span class="sxs-lookup"><span data-stu-id="24da9-107">Methods that take or produce a `char` array.</span></span>  
  
## <a name="unsupported-systemstring-static-methods"></a><span data-ttu-id="24da9-108">Metodi System.String statici non supportati</span><span class="sxs-lookup"><span data-stu-id="24da9-108">Unsupported System.String Static Methods</span></span>  
  
|<span data-ttu-id="24da9-109">Metodi System.String statici non supportati</span><span class="sxs-lookup"><span data-stu-id="24da9-109">Unsupported System.String Static Methods</span></span>|  
|----------------------------------------------|  
|<xref:System.String.Copy%28System.String%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.String%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%29?displayProperty=nameWithType>|  
|<xref:System.String.Compare%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%2CSystem.Boolean%2CSystem.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.String%29?displayProperty=nameWithType>|  
|<xref:System.String.CompareOrdinal%28System.String%2CSystem.Int32%2CSystem.String%2CSystem.Int32%2CSystem.Int32%29?displayProperty=nameWithType>|  
|<xref:System.String.Format%2A?displayProperty=nameWithType>|  
|<xref:System.String.Join%2A?displayProperty=nameWithType>|  
  
## <a name="unsupported-systemstring-non-static-methods"></a><span data-ttu-id="24da9-110">Metodi System.String non statici non supportati</span><span class="sxs-lookup"><span data-stu-id="24da9-110">Unsupported System.String Non-static Methods</span></span>  
  
|<span data-ttu-id="24da9-111">Metodi System.String non statici non supportati</span><span class="sxs-lookup"><span data-stu-id="24da9-111">Unsupported System.String Non-static Methods</span></span>|  
|---------------------------------------------------|  
|<xref:System.String.IndexOfAny%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.Split%2A?displayProperty=nameWithType>|  
|<xref:System.String.ToCharArray?displayProperty=nameWithType>|  
|<xref:System.String.ToUpper%28System.Globalization.CultureInfo%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimEnd%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
|<xref:System.String.TrimStart%28System.Char%5B%5D%29?displayProperty=nameWithType>|  
  
## <a name="differences-from-net"></a><span data-ttu-id="24da9-112">Differenze rispetto a .NET</span><span class="sxs-lookup"><span data-stu-id="24da9-112">Differences from .NET</span></span>  
  
-   <span data-ttu-id="24da9-113">Nelle query non vengono considerate le regole di confronto di SQL Server eventualmente attive sul server pertanto, per impostazione predefinita, verranno restituite regole di confronto dipendenti dalle impostazioni cultura e senza distinzione fra maiuscole e minuscole.</span><span class="sxs-lookup"><span data-stu-id="24da9-113">Queries do not account for SQL Server collations that might be in effect on the server, and therefore will provide culture-sensitive, case-insensitive comparisons by default.</span></span> <span data-ttu-id="24da9-114">Questo comportamento differisce dalla semantica predefinita con distinzione tra maiuscole e minuscole di .NET Framework.</span><span class="sxs-lookup"><span data-stu-id="24da9-114">This behavior differs from the default, case-sensitive semantics of the .NET Framework.</span></span>  
  
-   <span data-ttu-id="24da9-115">Quando `LastIndexOf` restituisce 0, significa che la stringa è `NULL` o la posizione trovata è 0.</span><span class="sxs-lookup"><span data-stu-id="24da9-115">When `LastIndexOf` returns 0, either the string is `NULL` or the found position is 0.</span></span>  
  
-   <span data-ttu-id="24da9-116">È possibile che vengano restituiti risultati imprevisti dalla concatenazione o da altre operazioni sulle stringhe a lunghezza fissa (`CHAR`, `NCHAR`), poiché a questi tipi viene applicata automaticamente la spaziatura interna nel database.</span><span class="sxs-lookup"><span data-stu-id="24da9-116">Unexpected results might be returned from concatenation or other operations on fixed-length strings (`CHAR`, `NCHAR`), because these types automatically have padding applied in the database.</span></span>  
  
-   <span data-ttu-id="24da9-117">Poiché molti metodi, ad esempio `Replace`, `ToLower`, `ToUpper` e l'indicizzatore del carattere, non dispongono di una conversione valida per le colonne `TEXT` o `NTEXT` e XML, se vengono convertiti normalmente si verifica un'eccezione `SqlExceptions`.</span><span class="sxs-lookup"><span data-stu-id="24da9-117">Because many methods, such as `Replace`, `ToLower`, `ToUpper`, and the character indexer, have no valid translation for `TEXT` or `NTEXT` columns and XML, `SqlExceptions` occur if translated normally.</span></span> <span data-ttu-id="24da9-118">Questo comportamento viene considerato accettabile per questi tipi.</span><span class="sxs-lookup"><span data-stu-id="24da9-118">This behavior is considered acceptable for these types.</span></span> <span data-ttu-id="24da9-119">Tuttavia è necessario che tutte le operazioni stringa corrispondano alla semantica Common Language Runtime (CLR) per `VARCHAR`, `NVARCHAR`, `VARCHAR(max)` e `NVARCHAR(max)`.</span><span class="sxs-lookup"><span data-stu-id="24da9-119">However, all string operations must match common language runtime (CLR) semantics for `VARCHAR`, `NVARCHAR`, `VARCHAR(max)`, and `NVARCHAR(max)`.</span></span>  
  
## <a name="see-also"></a><span data-ttu-id="24da9-120">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="24da9-120">See also</span></span>

- [<span data-ttu-id="24da9-121">Tipi di dati e funzioni</span><span class="sxs-lookup"><span data-stu-id="24da9-121">Data Types and Functions</span></span>](../../../../../../docs/framework/data/adonet/sql/linq/data-types-and-functions.md)
