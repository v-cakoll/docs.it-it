---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 0be8a279af6d8a43e03141e349d3efd5d35f8767
ms.translationtype: HT
ms.contentlocale: it-IT
ms.lasthandoff: 04/18/2019
ms.locfileid: "59164684"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="33cba-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="33cba-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="33cba-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="33cba-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="33cba-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="33cba-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="33cba-105">Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="33cba-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="33cba-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="33cba-106">Tables</span></span>  
  
-   <span data-ttu-id="33cba-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="33cba-107">Columns</span></span>  
  
-   <span data-ttu-id="33cba-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="33cba-108">Procedures</span></span>  
  
-   <span data-ttu-id="33cba-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33cba-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="33cba-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="33cba-110">Catalog</span></span>  
  
-   <span data-ttu-id="33cba-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="33cba-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="33cba-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="33cba-112">Tables</span></span>  
  
|<span data-ttu-id="33cba-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-113">ColumnName</span></span>|<span data-ttu-id="33cba-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-115">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-116">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-116">String</span></span>|  
|<span data-ttu-id="33cba-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-118">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-118">String</span></span>|  
|<span data-ttu-id="33cba-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-119">TABLE_NAME</span></span>|<span data-ttu-id="33cba-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-120">String</span></span>|  
|<span data-ttu-id="33cba-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-121">TABLE_TYPE</span></span>|<span data-ttu-id="33cba-122">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-122">String</span></span>|  
|<span data-ttu-id="33cba-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-123">TABLE_GUID</span></span>|<span data-ttu-id="33cba-124">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-124">Guid</span></span>|  
|<span data-ttu-id="33cba-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-125">DESCRIPTION</span></span>|<span data-ttu-id="33cba-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-126">String</span></span>|  
|<span data-ttu-id="33cba-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-127">TABLE_PROPID</span></span>|<span data-ttu-id="33cba-128">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-128">Int64</span></span>|  
|<span data-ttu-id="33cba-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-129">DATE_CREATED</span></span>|<span data-ttu-id="33cba-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-130">DateTime</span></span>|  
|<span data-ttu-id="33cba-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-131">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="33cba-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="33cba-133">Columns</span></span>  
  
|<span data-ttu-id="33cba-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-134">ColumnName</span></span>|<span data-ttu-id="33cba-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-136">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-137">String</span></span>|  
|<span data-ttu-id="33cba-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-139">String</span></span>|  
|<span data-ttu-id="33cba-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-140">TABLE_NAME</span></span>|<span data-ttu-id="33cba-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-141">String</span></span>|  
|<span data-ttu-id="33cba-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-142">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-143">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-143">String</span></span>|  
|<span data-ttu-id="33cba-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-144">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-145">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-145">Guid</span></span>|  
|<span data-ttu-id="33cba-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-146">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-147">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-147">Int64</span></span>|  
|<span data-ttu-id="33cba-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-149">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-149">Int64</span></span>|  
|<span data-ttu-id="33cba-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="33cba-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-151">Boolean</span></span>|  
|<span data-ttu-id="33cba-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="33cba-153">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-153">String</span></span>|  
|<span data-ttu-id="33cba-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="33cba-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="33cba-155">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-155">Int64</span></span>|  
|<span data-ttu-id="33cba-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-156">IS_NULLABLE</span></span>|<span data-ttu-id="33cba-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-157">Boolean</span></span>|  
|<span data-ttu-id="33cba-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-158">DATA_TYPE</span></span>|<span data-ttu-id="33cba-159">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-159">Int32</span></span>|  
|<span data-ttu-id="33cba-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-160">TYPE_GUID</span></span>|<span data-ttu-id="33cba-161">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-161">Guid</span></span>|  
|<span data-ttu-id="33cba-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="33cba-163">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-163">Int64</span></span>|  
|<span data-ttu-id="33cba-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="33cba-165">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-165">Int64</span></span>|  
|<span data-ttu-id="33cba-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="33cba-167">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-167">Int32</span></span>|  
|<span data-ttu-id="33cba-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="33cba-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="33cba-169">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-169">Int16</span></span>|  
|<span data-ttu-id="33cba-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="33cba-171">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-171">Int64</span></span>|  
|<span data-ttu-id="33cba-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="33cba-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-173">String</span></span>|  
|<span data-ttu-id="33cba-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="33cba-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-175">String</span></span>|  
|<span data-ttu-id="33cba-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="33cba-177">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-177">String</span></span>|  
|<span data-ttu-id="33cba-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="33cba-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-179">String</span></span>|  
|<span data-ttu-id="33cba-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="33cba-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-181">String</span></span>|  
|<span data-ttu-id="33cba-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-182">COLLATION_NAME</span></span>|<span data-ttu-id="33cba-183">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-183">String</span></span>|  
|<span data-ttu-id="33cba-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="33cba-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-185">String</span></span>|  
|<span data-ttu-id="33cba-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="33cba-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-187">String</span></span>|  
|<span data-ttu-id="33cba-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-188">DOMAIN_NAME</span></span>|<span data-ttu-id="33cba-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-189">String</span></span>|  
|<span data-ttu-id="33cba-190">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-190">DESCRIPTION</span></span>|<span data-ttu-id="33cba-191">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-191">String</span></span>|  
|<span data-ttu-id="33cba-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="33cba-192">COLUMN_LCID</span></span>|<span data-ttu-id="33cba-193">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-193">Int32</span></span>|  
|<span data-ttu-id="33cba-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="33cba-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="33cba-195">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-195">Int32</span></span>|  
|<span data-ttu-id="33cba-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="33cba-196">COLUMN_SORTID</span></span>|<span data-ttu-id="33cba-197">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-197">Int32</span></span>|  
|<span data-ttu-id="33cba-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="33cba-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="33cba-199">Byte[]</span></span>|  
|<span data-ttu-id="33cba-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="33cba-200">IS_COMPUTED</span></span>|<span data-ttu-id="33cba-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="33cba-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="33cba-202">Procedures</span></span>  
  
|<span data-ttu-id="33cba-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-203">ColumnName</span></span>|<span data-ttu-id="33cba-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="33cba-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-206">String</span></span>|  
|<span data-ttu-id="33cba-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="33cba-208">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-208">String</span></span>|  
|<span data-ttu-id="33cba-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="33cba-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-210">String</span></span>|  
|<span data-ttu-id="33cba-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="33cba-212">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-212">Int16</span></span>|  
|<span data-ttu-id="33cba-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="33cba-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="33cba-214">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-214">String</span></span>|  
|<span data-ttu-id="33cba-215">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-215">DESCRIPTION</span></span>|<span data-ttu-id="33cba-216">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-216">String</span></span>|  
|<span data-ttu-id="33cba-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-217">DATE_CREATED</span></span>|<span data-ttu-id="33cba-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-218">DateTime</span></span>|  
|<span data-ttu-id="33cba-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-219">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="33cba-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33cba-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="33cba-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-222">ColumnName</span></span>|<span data-ttu-id="33cba-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="33cba-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-225">String</span></span>|  
|<span data-ttu-id="33cba-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="33cba-227">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-227">String</span></span>|  
|<span data-ttu-id="33cba-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="33cba-229">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-229">String</span></span>|  
|<span data-ttu-id="33cba-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-230">PARAMETER_NAME</span></span>|<span data-ttu-id="33cba-231">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-231">String</span></span>|  
|<span data-ttu-id="33cba-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-233">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-233">Int32</span></span>|  
|<span data-ttu-id="33cba-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="33cba-235">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-235">Int32</span></span>|  
|<span data-ttu-id="33cba-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="33cba-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-237">Boolean</span></span>|  
|<span data-ttu-id="33cba-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="33cba-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-239">String</span></span>|  
|<span data-ttu-id="33cba-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-240">IS_NULLABLE</span></span>|<span data-ttu-id="33cba-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-241">Boolean</span></span>|  
|<span data-ttu-id="33cba-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-242">DATA_TYPE</span></span>|<span data-ttu-id="33cba-243">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-243">Int32</span></span>|  
|<span data-ttu-id="33cba-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="33cba-245">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-245">Int64</span></span>|  
|<span data-ttu-id="33cba-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="33cba-247">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-247">Int64</span></span>|  
|<span data-ttu-id="33cba-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="33cba-249">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-249">Int32</span></span>|  
|<span data-ttu-id="33cba-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="33cba-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="33cba-251">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-251">Int16</span></span>|  
|<span data-ttu-id="33cba-252">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-252">DESCRIPTION</span></span>|<span data-ttu-id="33cba-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-253">String</span></span>|  
|<span data-ttu-id="33cba-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-254">TYPE_NAME</span></span>|<span data-ttu-id="33cba-255">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-255">String</span></span>|  
|<span data-ttu-id="33cba-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="33cba-257">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="33cba-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="33cba-258">Catalog</span></span>  
  
|<span data-ttu-id="33cba-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-259">ColumnName</span></span>|<span data-ttu-id="33cba-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-261">CATALOG_NAME</span></span>|<span data-ttu-id="33cba-262">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-262">String</span></span>|  
|<span data-ttu-id="33cba-263">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-263">DESCRIPTION</span></span>|<span data-ttu-id="33cba-264">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="33cba-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="33cba-265">Indexes</span></span>  
  
|<span data-ttu-id="33cba-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-266">ColumnName</span></span>|<span data-ttu-id="33cba-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-268">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-269">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-269">String</span></span>|  
|<span data-ttu-id="33cba-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-271">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-271">String</span></span>|  
|<span data-ttu-id="33cba-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-272">TABLE_NAME</span></span>|<span data-ttu-id="33cba-273">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-273">String</span></span>|  
|<span data-ttu-id="33cba-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-274">INDEX_CATALOG</span></span>|<span data-ttu-id="33cba-275">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-275">String</span></span>|  
|<span data-ttu-id="33cba-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="33cba-277">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-277">String</span></span>|  
|<span data-ttu-id="33cba-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-278">INDEX_NAME</span></span>|<span data-ttu-id="33cba-279">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-279">String</span></span>|  
|<span data-ttu-id="33cba-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="33cba-280">PRIMARY_KEY</span></span>|<span data-ttu-id="33cba-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-281">Boolean</span></span>|  
|<span data-ttu-id="33cba-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="33cba-282">UNIQUE</span></span>|<span data-ttu-id="33cba-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-283">Boolean</span></span>|  
|<span data-ttu-id="33cba-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="33cba-284">CLUSTERED</span></span>|<span data-ttu-id="33cba-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-285">Boolean</span></span>|  
|<span data-ttu-id="33cba-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-286">TYPE</span></span>|<span data-ttu-id="33cba-287">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-287">Int32</span></span>|  
|<span data-ttu-id="33cba-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="33cba-288">FILL_FACTOR</span></span>|<span data-ttu-id="33cba-289">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-289">Int32</span></span>|  
|<span data-ttu-id="33cba-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="33cba-290">INITIAL_SIZE</span></span>|<span data-ttu-id="33cba-291">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-291">Int32</span></span>|  
|<span data-ttu-id="33cba-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="33cba-292">NULLS</span></span>|<span data-ttu-id="33cba-293">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-293">Int32</span></span>|  
|<span data-ttu-id="33cba-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="33cba-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="33cba-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-295">Boolean</span></span>|  
|<span data-ttu-id="33cba-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="33cba-296">AUTO_UPDATE</span></span>|<span data-ttu-id="33cba-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-297">Boolean</span></span>|  
|<span data-ttu-id="33cba-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-298">NULL_COLLATION</span></span>|<span data-ttu-id="33cba-299">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-299">Int32</span></span>|  
|<span data-ttu-id="33cba-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-301">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-301">Int64</span></span>|  
|<span data-ttu-id="33cba-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-302">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-303">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-303">String</span></span>|  
|<span data-ttu-id="33cba-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-304">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-305">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-305">Guid</span></span>|  
|<span data-ttu-id="33cba-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-306">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-307">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-307">Int64</span></span>|  
|<span data-ttu-id="33cba-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-308">COLLATION</span></span>|<span data-ttu-id="33cba-309">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-309">Int16</span></span>|  
|<span data-ttu-id="33cba-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="33cba-310">CARDINALITY</span></span>|<span data-ttu-id="33cba-311">Decimale</span><span class="sxs-lookup"><span data-stu-id="33cba-311">Decimal</span></span>|  
|<span data-ttu-id="33cba-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="33cba-312">PAGES</span></span>|<span data-ttu-id="33cba-313">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-313">Int32</span></span>|  
|<span data-ttu-id="33cba-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="33cba-314">FILTER_CONDITION</span></span>|<span data-ttu-id="33cba-315">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-315">String</span></span>|  
|<span data-ttu-id="33cba-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="33cba-316">INTEGRATED</span></span>|<span data-ttu-id="33cba-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="33cba-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="33cba-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="33cba-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="33cba-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="33cba-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="33cba-320">Tables</span></span>  
  
-   <span data-ttu-id="33cba-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="33cba-321">Columns</span></span>  
  
-   <span data-ttu-id="33cba-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="33cba-322">Procedures</span></span>  
  
-   <span data-ttu-id="33cba-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33cba-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="33cba-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="33cba-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="33cba-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="33cba-325">Views</span></span>  
  
-   <span data-ttu-id="33cba-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="33cba-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="33cba-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="33cba-327">Tables</span></span>  
  
|<span data-ttu-id="33cba-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-328">ColumnName</span></span>|<span data-ttu-id="33cba-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-330">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-331">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-331">String</span></span>|  
|<span data-ttu-id="33cba-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-333">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-333">String</span></span>|  
|<span data-ttu-id="33cba-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-334">TABLE_NAME</span></span>|<span data-ttu-id="33cba-335">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-335">String</span></span>|  
|<span data-ttu-id="33cba-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-336">TABLE_TYPE</span></span>|<span data-ttu-id="33cba-337">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-337">String</span></span>|  
|<span data-ttu-id="33cba-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-338">TABLE_GUID</span></span>|<span data-ttu-id="33cba-339">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-339">Guid</span></span>|  
|<span data-ttu-id="33cba-340">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-340">DESCRIPTION</span></span>|<span data-ttu-id="33cba-341">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-341">String</span></span>|  
|<span data-ttu-id="33cba-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-342">TABLE_PROPID</span></span>|<span data-ttu-id="33cba-343">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-343">Int64</span></span>|  
|<span data-ttu-id="33cba-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-344">DATE_CREATED</span></span>|<span data-ttu-id="33cba-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-345">DateTime</span></span>|  
|<span data-ttu-id="33cba-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-346">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="33cba-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="33cba-348">Columns</span></span>  
  
|<span data-ttu-id="33cba-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-349">ColumnName</span></span>|<span data-ttu-id="33cba-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-351">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-352">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-352">String</span></span>|  
|<span data-ttu-id="33cba-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-354">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-354">String</span></span>|  
|<span data-ttu-id="33cba-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-355">TABLE_NAME</span></span>|<span data-ttu-id="33cba-356">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-356">String</span></span>|  
|<span data-ttu-id="33cba-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-357">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-358">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-358">String</span></span>|  
|<span data-ttu-id="33cba-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-359">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-360">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-360">Guid</span></span>|  
|<span data-ttu-id="33cba-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-361">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-362">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-362">Int64</span></span>|  
|<span data-ttu-id="33cba-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-364">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-364">Int64</span></span>|  
|<span data-ttu-id="33cba-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="33cba-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-366">Boolean</span></span>|  
|<span data-ttu-id="33cba-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="33cba-368">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-368">String</span></span>|  
|<span data-ttu-id="33cba-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="33cba-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="33cba-370">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-370">Int64</span></span>|  
|<span data-ttu-id="33cba-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-371">IS_NULLABLE</span></span>|<span data-ttu-id="33cba-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-372">Boolean</span></span>|  
|<span data-ttu-id="33cba-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-373">DATA_TYPE</span></span>|<span data-ttu-id="33cba-374">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-374">Int32</span></span>|  
|<span data-ttu-id="33cba-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-375">TYPE_GUID</span></span>|<span data-ttu-id="33cba-376">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-376">Guid</span></span>|  
|<span data-ttu-id="33cba-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="33cba-378">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-378">Int64</span></span>|  
|<span data-ttu-id="33cba-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="33cba-380">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-380">Int64</span></span>|  
|<span data-ttu-id="33cba-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="33cba-382">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-382">Int32</span></span>|  
|<span data-ttu-id="33cba-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="33cba-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="33cba-384">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-384">Int16</span></span>|  
|<span data-ttu-id="33cba-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="33cba-386">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-386">Int64</span></span>|  
|<span data-ttu-id="33cba-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="33cba-388">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-388">String</span></span>|  
|<span data-ttu-id="33cba-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="33cba-390">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-390">String</span></span>|  
|<span data-ttu-id="33cba-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="33cba-392">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-392">String</span></span>|  
|<span data-ttu-id="33cba-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="33cba-394">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-394">String</span></span>|  
|<span data-ttu-id="33cba-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="33cba-396">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-396">String</span></span>|  
|<span data-ttu-id="33cba-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-397">COLLATION_NAME</span></span>|<span data-ttu-id="33cba-398">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-398">String</span></span>|  
|<span data-ttu-id="33cba-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="33cba-400">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-400">String</span></span>|  
|<span data-ttu-id="33cba-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="33cba-402">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-402">String</span></span>|  
|<span data-ttu-id="33cba-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-403">DOMAIN_NAME</span></span>|<span data-ttu-id="33cba-404">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-404">String</span></span>|  
|<span data-ttu-id="33cba-405">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-405">DESCRIPTION</span></span>|<span data-ttu-id="33cba-406">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="33cba-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="33cba-407">Procedures</span></span>  
  
|<span data-ttu-id="33cba-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-408">ColumnName</span></span>|<span data-ttu-id="33cba-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="33cba-411">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-411">String</span></span>|  
|<span data-ttu-id="33cba-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="33cba-413">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-413">String</span></span>|  
|<span data-ttu-id="33cba-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="33cba-415">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-415">String</span></span>|  
|<span data-ttu-id="33cba-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="33cba-417">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-417">Int16</span></span>|  
|<span data-ttu-id="33cba-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="33cba-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="33cba-419">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-419">String</span></span>|  
|<span data-ttu-id="33cba-420">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-420">DESCRIPTION</span></span>|<span data-ttu-id="33cba-421">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-421">String</span></span>|  
|<span data-ttu-id="33cba-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-422">DATE_CREATED</span></span>|<span data-ttu-id="33cba-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-423">DateTime</span></span>|  
|<span data-ttu-id="33cba-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-424">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="33cba-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="33cba-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="33cba-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-427">ColumnName</span></span>|<span data-ttu-id="33cba-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="33cba-430">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-430">String</span></span>|  
|<span data-ttu-id="33cba-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="33cba-432">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-432">String</span></span>|  
|<span data-ttu-id="33cba-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="33cba-434">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-434">String</span></span>|  
|<span data-ttu-id="33cba-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-435">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-436">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-436">String</span></span>|  
|<span data-ttu-id="33cba-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-437">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-438">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-438">Guid</span></span>|  
|<span data-ttu-id="33cba-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-439">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-440">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-440">Int64</span></span>|  
|<span data-ttu-id="33cba-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="33cba-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="33cba-442">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-442">Int64</span></span>|  
|<span data-ttu-id="33cba-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-444">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-444">Int64</span></span>|  
|<span data-ttu-id="33cba-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-445">IS_NULLABLE</span></span>|<span data-ttu-id="33cba-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-446">Boolean</span></span>|  
|<span data-ttu-id="33cba-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-447">DATA_TYPE</span></span>|<span data-ttu-id="33cba-448">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-448">Int32</span></span>|  
|<span data-ttu-id="33cba-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-449">TYPE_GUID</span></span>|<span data-ttu-id="33cba-450">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-450">Guid</span></span>|  
|<span data-ttu-id="33cba-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="33cba-452">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-452">Int64</span></span>|  
|<span data-ttu-id="33cba-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="33cba-454">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-454">Int64</span></span>|  
|<span data-ttu-id="33cba-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="33cba-456">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-456">Int32</span></span>|  
|<span data-ttu-id="33cba-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="33cba-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="33cba-458">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-458">Int16</span></span>|  
|<span data-ttu-id="33cba-459">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-459">DESCRIPTION</span></span>|<span data-ttu-id="33cba-460">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-460">String</span></span>|  
|<span data-ttu-id="33cba-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="33cba-461">OVERLOAD</span></span>|<span data-ttu-id="33cba-462">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="33cba-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="33cba-463">Views</span></span>  
  
|<span data-ttu-id="33cba-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-464">ColumnName</span></span>|<span data-ttu-id="33cba-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-466">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-467">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-467">String</span></span>|  
|<span data-ttu-id="33cba-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-469">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-469">String</span></span>|  
|<span data-ttu-id="33cba-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-470">TABLE_NAME</span></span>|<span data-ttu-id="33cba-471">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-471">String</span></span>|  
|<span data-ttu-id="33cba-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="33cba-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="33cba-473">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-473">String</span></span>|  
|<span data-ttu-id="33cba-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="33cba-474">CHECK_OPTION</span></span>|<span data-ttu-id="33cba-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-475">Boolean</span></span>|  
|<span data-ttu-id="33cba-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-476">IS_UPDATABLE</span></span>|<span data-ttu-id="33cba-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-477">Boolean</span></span>|  
|<span data-ttu-id="33cba-478">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-478">DESCRIPTION</span></span>|<span data-ttu-id="33cba-479">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-479">String</span></span>|  
|<span data-ttu-id="33cba-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-480">DATE_CREATED</span></span>|<span data-ttu-id="33cba-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-481">DateTime</span></span>|  
|<span data-ttu-id="33cba-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-482">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="33cba-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="33cba-484">Indexes</span></span>  
  
|<span data-ttu-id="33cba-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-485">ColumnName</span></span>|<span data-ttu-id="33cba-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-487">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-488">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-488">String</span></span>|  
|<span data-ttu-id="33cba-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-490">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-490">String</span></span>|  
|<span data-ttu-id="33cba-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-491">TABLE_NAME</span></span>|<span data-ttu-id="33cba-492">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-492">String</span></span>|  
|<span data-ttu-id="33cba-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-493">INDEX_CATALOG</span></span>|<span data-ttu-id="33cba-494">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-494">String</span></span>|  
|<span data-ttu-id="33cba-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="33cba-496">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-496">String</span></span>|  
|<span data-ttu-id="33cba-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-497">INDEX_NAME</span></span>|<span data-ttu-id="33cba-498">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-498">String</span></span>|  
|<span data-ttu-id="33cba-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="33cba-499">PRIMARY_KEY</span></span>|<span data-ttu-id="33cba-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-500">Boolean</span></span>|  
|<span data-ttu-id="33cba-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="33cba-501">UNIQUE</span></span>|<span data-ttu-id="33cba-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-502">Boolean</span></span>|  
|<span data-ttu-id="33cba-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="33cba-503">CLUSTERED</span></span>|<span data-ttu-id="33cba-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-504">Boolean</span></span>|  
|<span data-ttu-id="33cba-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-505">TYPE</span></span>|<span data-ttu-id="33cba-506">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-506">Int32</span></span>|  
|<span data-ttu-id="33cba-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="33cba-507">FILL_FACTOR</span></span>|<span data-ttu-id="33cba-508">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-508">Int32</span></span>|  
|<span data-ttu-id="33cba-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="33cba-509">INITIAL_SIZE</span></span>|<span data-ttu-id="33cba-510">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-510">Int32</span></span>|  
|<span data-ttu-id="33cba-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="33cba-511">NULLS</span></span>|<span data-ttu-id="33cba-512">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-512">Int32</span></span>|  
|<span data-ttu-id="33cba-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="33cba-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="33cba-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-514">Boolean</span></span>|  
|<span data-ttu-id="33cba-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="33cba-515">AUTO_UPDATE</span></span>|<span data-ttu-id="33cba-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-516">Boolean</span></span>|  
|<span data-ttu-id="33cba-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-517">NULL_COLLATION</span></span>|<span data-ttu-id="33cba-518">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-518">Int32</span></span>|  
|<span data-ttu-id="33cba-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-520">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-520">Int64</span></span>|  
|<span data-ttu-id="33cba-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-521">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-522">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-522">String</span></span>|  
|<span data-ttu-id="33cba-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-523">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-524">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-524">Guid</span></span>|  
|<span data-ttu-id="33cba-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-525">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-526">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-526">Int64</span></span>|  
|<span data-ttu-id="33cba-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-527">COLLATION</span></span>|<span data-ttu-id="33cba-528">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-528">Int16</span></span>|  
|<span data-ttu-id="33cba-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="33cba-529">CARDINALITY</span></span>|<span data-ttu-id="33cba-530">Decimale</span><span class="sxs-lookup"><span data-stu-id="33cba-530">Decimal</span></span>|  
|<span data-ttu-id="33cba-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="33cba-531">PAGES</span></span>|<span data-ttu-id="33cba-532">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-532">Int32</span></span>|  
|<span data-ttu-id="33cba-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="33cba-533">FILTER_CONDITION</span></span>|<span data-ttu-id="33cba-534">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-534">String</span></span>|  
|<span data-ttu-id="33cba-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="33cba-535">INTEGRATED</span></span>|<span data-ttu-id="33cba-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="33cba-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="33cba-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="33cba-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="33cba-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="33cba-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="33cba-539">Tables</span></span>  
  
-   <span data-ttu-id="33cba-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="33cba-540">Columns</span></span>  
  
-   <span data-ttu-id="33cba-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="33cba-541">Procedures</span></span>  
  
-   <span data-ttu-id="33cba-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="33cba-542">Views</span></span>  
  
-   <span data-ttu-id="33cba-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="33cba-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="33cba-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="33cba-544">Tables</span></span>  
  
|<span data-ttu-id="33cba-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-545">ColumnName</span></span>|<span data-ttu-id="33cba-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-547">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-548">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-548">String</span></span>|  
|<span data-ttu-id="33cba-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-550">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-550">String</span></span>|  
|<span data-ttu-id="33cba-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-551">TABLE_NAME</span></span>|<span data-ttu-id="33cba-552">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-552">String</span></span>|  
|<span data-ttu-id="33cba-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-553">TABLE_TYPE</span></span>|<span data-ttu-id="33cba-554">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-554">String</span></span>|  
|<span data-ttu-id="33cba-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-555">TABLE_GUID</span></span>|<span data-ttu-id="33cba-556">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-556">Guid</span></span>|  
|<span data-ttu-id="33cba-557">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-557">DESCRIPTION</span></span>|<span data-ttu-id="33cba-558">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-558">String</span></span>|  
|<span data-ttu-id="33cba-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-559">TABLE_PROPID</span></span>|<span data-ttu-id="33cba-560">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-560">Int64</span></span>|  
|<span data-ttu-id="33cba-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-561">DATE_CREATED</span></span>|<span data-ttu-id="33cba-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-562">DateTime</span></span>|  
|<span data-ttu-id="33cba-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-563">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="33cba-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="33cba-565">Columns</span></span>  
  
|<span data-ttu-id="33cba-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-566">ColumnName</span></span>|<span data-ttu-id="33cba-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-568">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-569">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-569">String</span></span>|  
|<span data-ttu-id="33cba-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-571">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-571">String</span></span>|  
|<span data-ttu-id="33cba-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-572">TABLE_NAME</span></span>|<span data-ttu-id="33cba-573">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-573">String</span></span>|  
|<span data-ttu-id="33cba-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-574">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-575">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-575">String</span></span>|  
|<span data-ttu-id="33cba-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-576">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-577">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-577">Guid</span></span>|  
|<span data-ttu-id="33cba-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-578">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-579">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-579">Int64</span></span>|  
|<span data-ttu-id="33cba-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-581">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-581">Int64</span></span>|  
|<span data-ttu-id="33cba-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="33cba-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-583">Boolean</span></span>|  
|<span data-ttu-id="33cba-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="33cba-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="33cba-585">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-585">String</span></span>|  
|<span data-ttu-id="33cba-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="33cba-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="33cba-587">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-587">Int64</span></span>|  
|<span data-ttu-id="33cba-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-588">IS_NULLABLE</span></span>|<span data-ttu-id="33cba-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-589">Boolean</span></span>|  
|<span data-ttu-id="33cba-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-590">DATA_TYPE</span></span>|<span data-ttu-id="33cba-591">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-591">Int32</span></span>|  
|<span data-ttu-id="33cba-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-592">TYPE_GUID</span></span>|<span data-ttu-id="33cba-593">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-593">Guid</span></span>|  
|<span data-ttu-id="33cba-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="33cba-595">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-595">Int64</span></span>|  
|<span data-ttu-id="33cba-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="33cba-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="33cba-597">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-597">Int64</span></span>|  
|<span data-ttu-id="33cba-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="33cba-599">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-599">Int32</span></span>|  
|<span data-ttu-id="33cba-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="33cba-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="33cba-601">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-601">Int16</span></span>|  
|<span data-ttu-id="33cba-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="33cba-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="33cba-603">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-603">Int64</span></span>|  
|<span data-ttu-id="33cba-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="33cba-605">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-605">String</span></span>|  
|<span data-ttu-id="33cba-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="33cba-607">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-607">String</span></span>|  
|<span data-ttu-id="33cba-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="33cba-609">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-609">String</span></span>|  
|<span data-ttu-id="33cba-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="33cba-611">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-611">String</span></span>|  
|<span data-ttu-id="33cba-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="33cba-613">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-613">String</span></span>|  
|<span data-ttu-id="33cba-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-614">COLLATION_NAME</span></span>|<span data-ttu-id="33cba-615">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-615">String</span></span>|  
|<span data-ttu-id="33cba-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="33cba-617">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-617">String</span></span>|  
|<span data-ttu-id="33cba-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="33cba-619">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-619">String</span></span>|  
|<span data-ttu-id="33cba-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-620">DOMAIN_NAME</span></span>|<span data-ttu-id="33cba-621">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-621">String</span></span>|  
|<span data-ttu-id="33cba-622">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-622">DESCRIPTION</span></span>|<span data-ttu-id="33cba-623">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="33cba-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="33cba-624">Procedures</span></span>  
  
|<span data-ttu-id="33cba-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-625">ColumnName</span></span>|<span data-ttu-id="33cba-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="33cba-628">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-628">String</span></span>|  
|<span data-ttu-id="33cba-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="33cba-630">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-630">String</span></span>|  
|<span data-ttu-id="33cba-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="33cba-632">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-632">String</span></span>|  
|<span data-ttu-id="33cba-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="33cba-634">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-634">Int16</span></span>|  
|<span data-ttu-id="33cba-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="33cba-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="33cba-636">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-636">String</span></span>|  
|<span data-ttu-id="33cba-637">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-637">DESCRIPTION</span></span>|<span data-ttu-id="33cba-638">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-638">String</span></span>|  
|<span data-ttu-id="33cba-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-639">DATE_CREATED</span></span>|<span data-ttu-id="33cba-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-640">DateTime</span></span>|  
|<span data-ttu-id="33cba-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-641">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="33cba-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="33cba-643">Views</span></span>  
  
|<span data-ttu-id="33cba-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-644">ColumnName</span></span>|<span data-ttu-id="33cba-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-646">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-647">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-647">String</span></span>|  
|<span data-ttu-id="33cba-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-649">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-649">String</span></span>|  
|<span data-ttu-id="33cba-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-650">TABLE_NAME</span></span>|<span data-ttu-id="33cba-651">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-651">String</span></span>|  
|<span data-ttu-id="33cba-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="33cba-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="33cba-653">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-653">String</span></span>|  
|<span data-ttu-id="33cba-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="33cba-654">CHECK_OPTION</span></span>|<span data-ttu-id="33cba-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-655">Boolean</span></span>|  
|<span data-ttu-id="33cba-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="33cba-656">IS_UPDATABLE</span></span>|<span data-ttu-id="33cba-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-657">Boolean</span></span>|  
|<span data-ttu-id="33cba-658">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="33cba-658">DESCRIPTION</span></span>|<span data-ttu-id="33cba-659">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-659">String</span></span>|  
|<span data-ttu-id="33cba-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="33cba-660">DATE_CREATED</span></span>|<span data-ttu-id="33cba-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-661">DateTime</span></span>|  
|<span data-ttu-id="33cba-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="33cba-662">DATE_MODIFIED</span></span>|<span data-ttu-id="33cba-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="33cba-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="33cba-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="33cba-664">Indexes</span></span>  
  
|<span data-ttu-id="33cba-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="33cba-665">ColumnName</span></span>|<span data-ttu-id="33cba-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="33cba-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-667">TABLE_CATALOG</span></span>|<span data-ttu-id="33cba-668">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-668">String</span></span>|  
|<span data-ttu-id="33cba-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="33cba-670">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-670">String</span></span>|  
|<span data-ttu-id="33cba-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-671">TABLE_NAME</span></span>|<span data-ttu-id="33cba-672">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-672">String</span></span>|  
|<span data-ttu-id="33cba-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="33cba-673">INDEX_CATALOG</span></span>|<span data-ttu-id="33cba-674">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-674">String</span></span>|  
|<span data-ttu-id="33cba-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="33cba-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="33cba-676">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-676">String</span></span>|  
|<span data-ttu-id="33cba-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-677">INDEX_NAME</span></span>|<span data-ttu-id="33cba-678">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-678">String</span></span>|  
|<span data-ttu-id="33cba-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="33cba-679">PRIMARY_KEY</span></span>|<span data-ttu-id="33cba-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-680">Boolean</span></span>|  
|<span data-ttu-id="33cba-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="33cba-681">UNIQUE</span></span>|<span data-ttu-id="33cba-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-682">Boolean</span></span>|  
|<span data-ttu-id="33cba-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="33cba-683">CLUSTERED</span></span>|<span data-ttu-id="33cba-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-684">Boolean</span></span>|  
|<span data-ttu-id="33cba-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="33cba-685">TYPE</span></span>|<span data-ttu-id="33cba-686">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-686">Int32</span></span>|  
|<span data-ttu-id="33cba-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="33cba-687">FILL_FACTOR</span></span>|<span data-ttu-id="33cba-688">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-688">Int32</span></span>|  
|<span data-ttu-id="33cba-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="33cba-689">INITIAL_SIZE</span></span>|<span data-ttu-id="33cba-690">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-690">Int32</span></span>|  
|<span data-ttu-id="33cba-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="33cba-691">NULLS</span></span>|<span data-ttu-id="33cba-692">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-692">Int32</span></span>|  
|<span data-ttu-id="33cba-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="33cba-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="33cba-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-694">Boolean</span></span>|  
|<span data-ttu-id="33cba-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="33cba-695">AUTO_UPDATE</span></span>|<span data-ttu-id="33cba-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-696">Boolean</span></span>|  
|<span data-ttu-id="33cba-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-697">NULL_COLLATION</span></span>|<span data-ttu-id="33cba-698">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-698">Int32</span></span>|  
|<span data-ttu-id="33cba-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="33cba-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="33cba-700">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-700">Int64</span></span>|  
|<span data-ttu-id="33cba-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="33cba-701">COLUMN_NAME</span></span>|<span data-ttu-id="33cba-702">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-702">String</span></span>|  
|<span data-ttu-id="33cba-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-703">COLUMN_GUID</span></span>|<span data-ttu-id="33cba-704">GUID</span><span class="sxs-lookup"><span data-stu-id="33cba-704">Guid</span></span>|  
|<span data-ttu-id="33cba-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="33cba-705">COLUMN_PROPID</span></span>|<span data-ttu-id="33cba-706">Int64</span><span class="sxs-lookup"><span data-stu-id="33cba-706">Int64</span></span>|  
|<span data-ttu-id="33cba-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="33cba-707">COLLATION</span></span>|<span data-ttu-id="33cba-708">Int16</span><span class="sxs-lookup"><span data-stu-id="33cba-708">Int16</span></span>|  
|<span data-ttu-id="33cba-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="33cba-709">CARDINALITY</span></span>|<span data-ttu-id="33cba-710">Decimale</span><span class="sxs-lookup"><span data-stu-id="33cba-710">Decimal</span></span>|  
|<span data-ttu-id="33cba-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="33cba-711">PAGES</span></span>|<span data-ttu-id="33cba-712">Int32</span><span class="sxs-lookup"><span data-stu-id="33cba-712">Int32</span></span>|  
|<span data-ttu-id="33cba-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="33cba-713">FILTER_CONDITION</span></span>|<span data-ttu-id="33cba-714">Stringa</span><span class="sxs-lookup"><span data-stu-id="33cba-714">String</span></span>|  
|<span data-ttu-id="33cba-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="33cba-715">INTEGRATED</span></span>|<span data-ttu-id="33cba-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="33cba-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="33cba-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="33cba-717">See also</span></span>

- [<span data-ttu-id="33cba-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="33cba-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
