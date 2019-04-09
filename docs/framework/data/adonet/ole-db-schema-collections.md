---
title: Raccolte di schemi OLE DB
ms.date: 03/30/2017
ms.assetid: 6380c36b-658e-4d67-91e8-7131ef4a7c2c
ms.openlocfilehash: 6dc187b0a876d9e167a74f2381db156dde2764fe
ms.sourcegitcommit: 5b6d778ebb269ee6684fb57ad69a8c28b06235b9
ms.translationtype: MT
ms.contentlocale: it-IT
ms.lasthandoff: 04/08/2019
ms.locfileid: "59164684"
---
# <a name="ole-db-schema-collections"></a><span data-ttu-id="427fa-102">Raccolte di schemi OLE DB</span><span class="sxs-lookup"><span data-stu-id="427fa-102">OLE DB Schema Collections</span></span>
<span data-ttu-id="427fa-103">Contenuto della sezione viene descritto il supporto delle raccolte di schemi per i provider OLE DB per Microsoft SQL Server, Oracle e Microsoft Jet.</span><span class="sxs-lookup"><span data-stu-id="427fa-103">This section discusses schema collection support for the OLE DB providers for Microsoft SQL Server, Oracle, and Microsoft Jet.</span></span>  
  
## <a name="microsoft-sql-server-ole-db-provider"></a><span data-ttu-id="427fa-104">Provider OLE DB per Microsoft SQL Server</span><span class="sxs-lookup"><span data-stu-id="427fa-104">Microsoft SQL Server OLE DB Provider</span></span>  
 <span data-ttu-id="427fa-105">Il Driver OLE DB Microsoft SQL Server supporta le seguenti raccolte di schemi specifici oltre alle raccolte di schemi comuni:</span><span class="sxs-lookup"><span data-stu-id="427fa-105">The Microsoft SQL Server OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="427fa-106">Tabelle</span><span class="sxs-lookup"><span data-stu-id="427fa-106">Tables</span></span>  
  
-   <span data-ttu-id="427fa-107">Colonne</span><span class="sxs-lookup"><span data-stu-id="427fa-107">Columns</span></span>  
  
-   <span data-ttu-id="427fa-108">Procedure</span><span class="sxs-lookup"><span data-stu-id="427fa-108">Procedures</span></span>  
  
-   <span data-ttu-id="427fa-109">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="427fa-109">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="427fa-110">Catalog</span><span class="sxs-lookup"><span data-stu-id="427fa-110">Catalog</span></span>  
  
-   <span data-ttu-id="427fa-111">Indexes</span><span class="sxs-lookup"><span data-stu-id="427fa-111">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="427fa-112">Tabelle</span><span class="sxs-lookup"><span data-stu-id="427fa-112">Tables</span></span>  
  
|<span data-ttu-id="427fa-113">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-113">ColumnName</span></span>|<span data-ttu-id="427fa-114">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-114">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-115">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-115">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-116">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-116">String</span></span>|  
|<span data-ttu-id="427fa-117">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-117">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-118">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-118">String</span></span>|  
|<span data-ttu-id="427fa-119">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-119">TABLE_NAME</span></span>|<span data-ttu-id="427fa-120">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-120">String</span></span>|  
|<span data-ttu-id="427fa-121">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-121">TABLE_TYPE</span></span>|<span data-ttu-id="427fa-122">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-122">String</span></span>|  
|<span data-ttu-id="427fa-123">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-123">TABLE_GUID</span></span>|<span data-ttu-id="427fa-124">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-124">Guid</span></span>|  
|<span data-ttu-id="427fa-125">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-125">DESCRIPTION</span></span>|<span data-ttu-id="427fa-126">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-126">String</span></span>|  
|<span data-ttu-id="427fa-127">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-127">TABLE_PROPID</span></span>|<span data-ttu-id="427fa-128">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-128">Int64</span></span>|  
|<span data-ttu-id="427fa-129">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-129">DATE_CREATED</span></span>|<span data-ttu-id="427fa-130">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-130">DateTime</span></span>|  
|<span data-ttu-id="427fa-131">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-131">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-132">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-132">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="427fa-133">Colonne</span><span class="sxs-lookup"><span data-stu-id="427fa-133">Columns</span></span>  
  
|<span data-ttu-id="427fa-134">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-134">ColumnName</span></span>|<span data-ttu-id="427fa-135">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-135">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-136">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-136">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-137">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-137">String</span></span>|  
|<span data-ttu-id="427fa-138">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-138">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-139">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-139">String</span></span>|  
|<span data-ttu-id="427fa-140">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-140">TABLE_NAME</span></span>|<span data-ttu-id="427fa-141">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-141">String</span></span>|  
|<span data-ttu-id="427fa-142">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-142">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-143">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-143">String</span></span>|  
|<span data-ttu-id="427fa-144">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-144">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-145">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-145">Guid</span></span>|  
|<span data-ttu-id="427fa-146">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-146">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-147">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-147">Int64</span></span>|  
|<span data-ttu-id="427fa-148">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-148">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-149">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-149">Int64</span></span>|  
|<span data-ttu-id="427fa-150">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-150">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="427fa-151">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-151">Boolean</span></span>|  
|<span data-ttu-id="427fa-152">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-152">COLUMN_DEFAULT</span></span>|<span data-ttu-id="427fa-153">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-153">String</span></span>|  
|<span data-ttu-id="427fa-154">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="427fa-154">COLUMN_FLAGS</span></span>|<span data-ttu-id="427fa-155">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-155">Int64</span></span>|  
|<span data-ttu-id="427fa-156">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-156">IS_NULLABLE</span></span>|<span data-ttu-id="427fa-157">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-157">Boolean</span></span>|  
|<span data-ttu-id="427fa-158">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-158">DATA_TYPE</span></span>|<span data-ttu-id="427fa-159">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-159">Int32</span></span>|  
|<span data-ttu-id="427fa-160">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-160">TYPE_GUID</span></span>|<span data-ttu-id="427fa-161">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-161">Guid</span></span>|  
|<span data-ttu-id="427fa-162">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-162">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="427fa-163">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-163">Int64</span></span>|  
|<span data-ttu-id="427fa-164">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-164">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="427fa-165">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-165">Int64</span></span>|  
|<span data-ttu-id="427fa-166">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-166">NUMERIC_PRECISION</span></span>|<span data-ttu-id="427fa-167">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-167">Int32</span></span>|  
|<span data-ttu-id="427fa-168">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="427fa-168">NUMERIC_SCALE</span></span>|<span data-ttu-id="427fa-169">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-169">Int16</span></span>|  
|<span data-ttu-id="427fa-170">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-170">DATETIME_PRECISION</span></span>|<span data-ttu-id="427fa-171">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-171">Int64</span></span>|  
|<span data-ttu-id="427fa-172">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-172">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="427fa-173">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-173">String</span></span>|  
|<span data-ttu-id="427fa-174">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-174">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="427fa-175">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-175">String</span></span>|  
|<span data-ttu-id="427fa-176">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-176">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="427fa-177">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-177">String</span></span>|  
|<span data-ttu-id="427fa-178">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-178">COLLATION_CATALOG</span></span>|<span data-ttu-id="427fa-179">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-179">String</span></span>|  
|<span data-ttu-id="427fa-180">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-180">COLLATION_SCHEMA</span></span>|<span data-ttu-id="427fa-181">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-181">String</span></span>|  
|<span data-ttu-id="427fa-182">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-182">COLLATION_NAME</span></span>|<span data-ttu-id="427fa-183">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-183">String</span></span>|  
|<span data-ttu-id="427fa-184">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-184">DOMAIN_CATALOG</span></span>|<span data-ttu-id="427fa-185">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-185">String</span></span>|  
|<span data-ttu-id="427fa-186">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-186">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="427fa-187">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-187">String</span></span>|  
|<span data-ttu-id="427fa-188">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-188">DOMAIN_NAME</span></span>|<span data-ttu-id="427fa-189">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-189">String</span></span>|  
|<span data-ttu-id="427fa-190">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-190">DESCRIPTION</span></span>|<span data-ttu-id="427fa-191">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-191">String</span></span>|  
|<span data-ttu-id="427fa-192">COLUMN_LCID</span><span class="sxs-lookup"><span data-stu-id="427fa-192">COLUMN_LCID</span></span>|<span data-ttu-id="427fa-193">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-193">Int32</span></span>|  
|<span data-ttu-id="427fa-194">COLUMN_COMPFLAGS</span><span class="sxs-lookup"><span data-stu-id="427fa-194">COLUMN_COMPFLAGS</span></span>|<span data-ttu-id="427fa-195">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-195">Int32</span></span>|  
|<span data-ttu-id="427fa-196">COLUMN_SORTID</span><span class="sxs-lookup"><span data-stu-id="427fa-196">COLUMN_SORTID</span></span>|<span data-ttu-id="427fa-197">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-197">Int32</span></span>|  
|<span data-ttu-id="427fa-198">COLUMN_TDSCOLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-198">COLUMN_TDSCOLLATION</span></span>|<span data-ttu-id="427fa-199">Byte[]</span><span class="sxs-lookup"><span data-stu-id="427fa-199">Byte[]</span></span>|  
|<span data-ttu-id="427fa-200">IS_COMPUTED</span><span class="sxs-lookup"><span data-stu-id="427fa-200">IS_COMPUTED</span></span>|<span data-ttu-id="427fa-201">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-201">Boolean</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="427fa-202">Procedure</span><span class="sxs-lookup"><span data-stu-id="427fa-202">Procedures</span></span>  
  
|<span data-ttu-id="427fa-203">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-203">ColumnName</span></span>|<span data-ttu-id="427fa-204">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-204">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-205">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-205">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="427fa-206">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-206">String</span></span>|  
|<span data-ttu-id="427fa-207">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-207">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="427fa-208">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-208">String</span></span>|  
|<span data-ttu-id="427fa-209">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-209">PROCEDURE_NAME</span></span>|<span data-ttu-id="427fa-210">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-210">String</span></span>|  
|<span data-ttu-id="427fa-211">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-211">PROCEDURE_TYPE</span></span>|<span data-ttu-id="427fa-212">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-212">Int16</span></span>|  
|<span data-ttu-id="427fa-213">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="427fa-213">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="427fa-214">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-214">String</span></span>|  
|<span data-ttu-id="427fa-215">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-215">DESCRIPTION</span></span>|<span data-ttu-id="427fa-216">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-216">String</span></span>|  
|<span data-ttu-id="427fa-217">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-217">DATE_CREATED</span></span>|<span data-ttu-id="427fa-218">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-218">DateTime</span></span>|  
|<span data-ttu-id="427fa-219">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-219">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-220">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-220">DateTime</span></span>|  
  
### <a name="procedureparameters"></a><span data-ttu-id="427fa-221">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="427fa-221">ProcedureParameters</span></span>  
  
|<span data-ttu-id="427fa-222">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-222">ColumnName</span></span>|<span data-ttu-id="427fa-223">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-223">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-224">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-224">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="427fa-225">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-225">String</span></span>|  
|<span data-ttu-id="427fa-226">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-226">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="427fa-227">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-227">String</span></span>|  
|<span data-ttu-id="427fa-228">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-228">PROCEDURE_NAME</span></span>|<span data-ttu-id="427fa-229">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-229">String</span></span>|  
|<span data-ttu-id="427fa-230">PARAMETER_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-230">PARAMETER_NAME</span></span>|<span data-ttu-id="427fa-231">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-231">String</span></span>|  
|<span data-ttu-id="427fa-232">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-232">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-233">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-233">Int32</span></span>|  
|<span data-ttu-id="427fa-234">PARAMETER_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-234">PARAMETER_TYPE</span></span>|<span data-ttu-id="427fa-235">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-235">Int32</span></span>|  
|<span data-ttu-id="427fa-236">PARAMETER_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-236">PARAMETER_HASDEFAULT</span></span>|<span data-ttu-id="427fa-237">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-237">Boolean</span></span>|  
|<span data-ttu-id="427fa-238">PARAMETER_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-238">PARAMETER_DEFAULT</span></span>|<span data-ttu-id="427fa-239">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-239">String</span></span>|  
|<span data-ttu-id="427fa-240">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-240">IS_NULLABLE</span></span>|<span data-ttu-id="427fa-241">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-241">Boolean</span></span>|  
|<span data-ttu-id="427fa-242">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-242">DATA_TYPE</span></span>|<span data-ttu-id="427fa-243">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-243">Int32</span></span>|  
|<span data-ttu-id="427fa-244">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-244">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="427fa-245">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-245">Int64</span></span>|  
|<span data-ttu-id="427fa-246">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-246">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="427fa-247">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-247">Int64</span></span>|  
|<span data-ttu-id="427fa-248">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-248">NUMERIC_PRECISION</span></span>|<span data-ttu-id="427fa-249">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-249">Int32</span></span>|  
|<span data-ttu-id="427fa-250">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="427fa-250">NUMERIC_SCALE</span></span>|<span data-ttu-id="427fa-251">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-251">Int16</span></span>|  
|<span data-ttu-id="427fa-252">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-252">DESCRIPTION</span></span>|<span data-ttu-id="427fa-253">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-253">String</span></span>|  
|<span data-ttu-id="427fa-254">TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-254">TYPE_NAME</span></span>|<span data-ttu-id="427fa-255">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-255">String</span></span>|  
|<span data-ttu-id="427fa-256">LOCAL_TYPE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-256">LOCAL_TYPE_NAME</span></span>|<span data-ttu-id="427fa-257">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-257">String</span></span>|  
  
### <a name="catalog"></a><span data-ttu-id="427fa-258">Catalog</span><span class="sxs-lookup"><span data-stu-id="427fa-258">Catalog</span></span>  
  
|<span data-ttu-id="427fa-259">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-259">ColumnName</span></span>|<span data-ttu-id="427fa-260">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-260">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-261">CATALOG_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-261">CATALOG_NAME</span></span>|<span data-ttu-id="427fa-262">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-262">String</span></span>|  
|<span data-ttu-id="427fa-263">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-263">DESCRIPTION</span></span>|<span data-ttu-id="427fa-264">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-264">String</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="427fa-265">Indexes</span><span class="sxs-lookup"><span data-stu-id="427fa-265">Indexes</span></span>  
  
|<span data-ttu-id="427fa-266">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-266">ColumnName</span></span>|<span data-ttu-id="427fa-267">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-267">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-268">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-268">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-269">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-269">String</span></span>|  
|<span data-ttu-id="427fa-270">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-270">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-271">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-271">String</span></span>|  
|<span data-ttu-id="427fa-272">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-272">TABLE_NAME</span></span>|<span data-ttu-id="427fa-273">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-273">String</span></span>|  
|<span data-ttu-id="427fa-274">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-274">INDEX_CATALOG</span></span>|<span data-ttu-id="427fa-275">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-275">String</span></span>|  
|<span data-ttu-id="427fa-276">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-276">INDEX_SCHEMA</span></span>|<span data-ttu-id="427fa-277">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-277">String</span></span>|  
|<span data-ttu-id="427fa-278">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-278">INDEX_NAME</span></span>|<span data-ttu-id="427fa-279">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-279">String</span></span>|  
|<span data-ttu-id="427fa-280">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="427fa-280">PRIMARY_KEY</span></span>|<span data-ttu-id="427fa-281">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-281">Boolean</span></span>|  
|<span data-ttu-id="427fa-282">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="427fa-282">UNIQUE</span></span>|<span data-ttu-id="427fa-283">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-283">Boolean</span></span>|  
|<span data-ttu-id="427fa-284">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="427fa-284">CLUSTERED</span></span>|<span data-ttu-id="427fa-285">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-285">Boolean</span></span>|  
|<span data-ttu-id="427fa-286">TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-286">TYPE</span></span>|<span data-ttu-id="427fa-287">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-287">Int32</span></span>|  
|<span data-ttu-id="427fa-288">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="427fa-288">FILL_FACTOR</span></span>|<span data-ttu-id="427fa-289">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-289">Int32</span></span>|  
|<span data-ttu-id="427fa-290">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="427fa-290">INITIAL_SIZE</span></span>|<span data-ttu-id="427fa-291">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-291">Int32</span></span>|  
|<span data-ttu-id="427fa-292">NULLS</span><span class="sxs-lookup"><span data-stu-id="427fa-292">NULLS</span></span>|<span data-ttu-id="427fa-293">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-293">Int32</span></span>|  
|<span data-ttu-id="427fa-294">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="427fa-294">SORT_BOOKMARKS</span></span>|<span data-ttu-id="427fa-295">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-295">Boolean</span></span>|  
|<span data-ttu-id="427fa-296">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="427fa-296">AUTO_UPDATE</span></span>|<span data-ttu-id="427fa-297">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-297">Boolean</span></span>|  
|<span data-ttu-id="427fa-298">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-298">NULL_COLLATION</span></span>|<span data-ttu-id="427fa-299">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-299">Int32</span></span>|  
|<span data-ttu-id="427fa-300">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-300">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-301">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-301">Int64</span></span>|  
|<span data-ttu-id="427fa-302">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-302">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-303">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-303">String</span></span>|  
|<span data-ttu-id="427fa-304">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-304">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-305">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-305">Guid</span></span>|  
|<span data-ttu-id="427fa-306">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-306">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-307">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-307">Int64</span></span>|  
|<span data-ttu-id="427fa-308">COLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-308">COLLATION</span></span>|<span data-ttu-id="427fa-309">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-309">Int16</span></span>|  
|<span data-ttu-id="427fa-310">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="427fa-310">CARDINALITY</span></span>|<span data-ttu-id="427fa-311">Decimale</span><span class="sxs-lookup"><span data-stu-id="427fa-311">Decimal</span></span>|  
|<span data-ttu-id="427fa-312">PAGES</span><span class="sxs-lookup"><span data-stu-id="427fa-312">PAGES</span></span>|<span data-ttu-id="427fa-313">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-313">Int32</span></span>|  
|<span data-ttu-id="427fa-314">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="427fa-314">FILTER_CONDITION</span></span>|<span data-ttu-id="427fa-315">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-315">String</span></span>|  
|<span data-ttu-id="427fa-316">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="427fa-316">INTEGRATED</span></span>|<span data-ttu-id="427fa-317">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-317">Boolean</span></span>|  
  
## <a name="microsoft-oracle-ole-db-provider"></a><span data-ttu-id="427fa-318">Provider OLE DB per Microsoft Oracle</span><span class="sxs-lookup"><span data-stu-id="427fa-318">Microsoft Oracle OLE DB Provider</span></span>  
 <span data-ttu-id="427fa-319">Oltre alle raccolte di schemi comuni, il driver OLE DB per Microsoft Oracle supporta le seguenti raccolte di schemi specifici:</span><span class="sxs-lookup"><span data-stu-id="427fa-319">The Microsoft Oracle OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="427fa-320">Tabelle</span><span class="sxs-lookup"><span data-stu-id="427fa-320">Tables</span></span>  
  
-   <span data-ttu-id="427fa-321">Colonne</span><span class="sxs-lookup"><span data-stu-id="427fa-321">Columns</span></span>  
  
-   <span data-ttu-id="427fa-322">Procedure</span><span class="sxs-lookup"><span data-stu-id="427fa-322">Procedures</span></span>  
  
-   <span data-ttu-id="427fa-323">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="427fa-323">ProcedureColumns</span></span>  
  
-   <span data-ttu-id="427fa-324">ProcedureParameters</span><span class="sxs-lookup"><span data-stu-id="427fa-324">ProcedureParameters</span></span>  
  
-   <span data-ttu-id="427fa-325">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="427fa-325">Views</span></span>  
  
-   <span data-ttu-id="427fa-326">Indexes</span><span class="sxs-lookup"><span data-stu-id="427fa-326">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="427fa-327">Tabelle</span><span class="sxs-lookup"><span data-stu-id="427fa-327">Tables</span></span>  
  
|<span data-ttu-id="427fa-328">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-328">ColumnName</span></span>|<span data-ttu-id="427fa-329">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-329">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-330">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-330">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-331">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-331">String</span></span>|  
|<span data-ttu-id="427fa-332">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-332">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-333">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-333">String</span></span>|  
|<span data-ttu-id="427fa-334">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-334">TABLE_NAME</span></span>|<span data-ttu-id="427fa-335">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-335">String</span></span>|  
|<span data-ttu-id="427fa-336">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-336">TABLE_TYPE</span></span>|<span data-ttu-id="427fa-337">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-337">String</span></span>|  
|<span data-ttu-id="427fa-338">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-338">TABLE_GUID</span></span>|<span data-ttu-id="427fa-339">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-339">Guid</span></span>|  
|<span data-ttu-id="427fa-340">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-340">DESCRIPTION</span></span>|<span data-ttu-id="427fa-341">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-341">String</span></span>|  
|<span data-ttu-id="427fa-342">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-342">TABLE_PROPID</span></span>|<span data-ttu-id="427fa-343">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-343">Int64</span></span>|  
|<span data-ttu-id="427fa-344">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-344">DATE_CREATED</span></span>|<span data-ttu-id="427fa-345">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-345">DateTime</span></span>|  
|<span data-ttu-id="427fa-346">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-346">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-347">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-347">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="427fa-348">Colonne</span><span class="sxs-lookup"><span data-stu-id="427fa-348">Columns</span></span>  
  
|<span data-ttu-id="427fa-349">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-349">ColumnName</span></span>|<span data-ttu-id="427fa-350">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-350">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-351">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-351">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-352">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-352">String</span></span>|  
|<span data-ttu-id="427fa-353">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-353">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-354">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-354">String</span></span>|  
|<span data-ttu-id="427fa-355">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-355">TABLE_NAME</span></span>|<span data-ttu-id="427fa-356">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-356">String</span></span>|  
|<span data-ttu-id="427fa-357">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-357">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-358">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-358">String</span></span>|  
|<span data-ttu-id="427fa-359">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-359">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-360">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-360">Guid</span></span>|  
|<span data-ttu-id="427fa-361">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-361">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-362">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-362">Int64</span></span>|  
|<span data-ttu-id="427fa-363">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-363">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-364">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-364">Int64</span></span>|  
|<span data-ttu-id="427fa-365">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-365">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="427fa-366">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-366">Boolean</span></span>|  
|<span data-ttu-id="427fa-367">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-367">COLUMN_DEFAULT</span></span>|<span data-ttu-id="427fa-368">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-368">String</span></span>|  
|<span data-ttu-id="427fa-369">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="427fa-369">COLUMN_FLAGS</span></span>|<span data-ttu-id="427fa-370">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-370">Int64</span></span>|  
|<span data-ttu-id="427fa-371">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-371">IS_NULLABLE</span></span>|<span data-ttu-id="427fa-372">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-372">Boolean</span></span>|  
|<span data-ttu-id="427fa-373">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-373">DATA_TYPE</span></span>|<span data-ttu-id="427fa-374">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-374">Int32</span></span>|  
|<span data-ttu-id="427fa-375">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-375">TYPE_GUID</span></span>|<span data-ttu-id="427fa-376">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-376">Guid</span></span>|  
|<span data-ttu-id="427fa-377">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-377">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="427fa-378">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-378">Int64</span></span>|  
|<span data-ttu-id="427fa-379">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-379">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="427fa-380">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-380">Int64</span></span>|  
|<span data-ttu-id="427fa-381">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-381">NUMERIC_PRECISION</span></span>|<span data-ttu-id="427fa-382">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-382">Int32</span></span>|  
|<span data-ttu-id="427fa-383">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="427fa-383">NUMERIC_SCALE</span></span>|<span data-ttu-id="427fa-384">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-384">Int16</span></span>|  
|<span data-ttu-id="427fa-385">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-385">DATETIME_PRECISION</span></span>|<span data-ttu-id="427fa-386">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-386">Int64</span></span>|  
|<span data-ttu-id="427fa-387">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-387">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="427fa-388">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-388">String</span></span>|  
|<span data-ttu-id="427fa-389">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-389">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="427fa-390">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-390">String</span></span>|  
|<span data-ttu-id="427fa-391">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-391">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="427fa-392">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-392">String</span></span>|  
|<span data-ttu-id="427fa-393">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-393">COLLATION_CATALOG</span></span>|<span data-ttu-id="427fa-394">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-394">String</span></span>|  
|<span data-ttu-id="427fa-395">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-395">COLLATION_SCHEMA</span></span>|<span data-ttu-id="427fa-396">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-396">String</span></span>|  
|<span data-ttu-id="427fa-397">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-397">COLLATION_NAME</span></span>|<span data-ttu-id="427fa-398">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-398">String</span></span>|  
|<span data-ttu-id="427fa-399">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-399">DOMAIN_CATALOG</span></span>|<span data-ttu-id="427fa-400">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-400">String</span></span>|  
|<span data-ttu-id="427fa-401">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-401">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="427fa-402">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-402">String</span></span>|  
|<span data-ttu-id="427fa-403">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-403">DOMAIN_NAME</span></span>|<span data-ttu-id="427fa-404">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-404">String</span></span>|  
|<span data-ttu-id="427fa-405">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-405">DESCRIPTION</span></span>|<span data-ttu-id="427fa-406">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-406">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="427fa-407">Procedure</span><span class="sxs-lookup"><span data-stu-id="427fa-407">Procedures</span></span>  
  
|<span data-ttu-id="427fa-408">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-408">ColumnName</span></span>|<span data-ttu-id="427fa-409">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-409">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-410">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-410">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="427fa-411">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-411">String</span></span>|  
|<span data-ttu-id="427fa-412">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-412">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="427fa-413">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-413">String</span></span>|  
|<span data-ttu-id="427fa-414">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-414">PROCEDURE_NAME</span></span>|<span data-ttu-id="427fa-415">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-415">String</span></span>|  
|<span data-ttu-id="427fa-416">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-416">PROCEDURE_TYPE</span></span>|<span data-ttu-id="427fa-417">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-417">Int16</span></span>|  
|<span data-ttu-id="427fa-418">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="427fa-418">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="427fa-419">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-419">String</span></span>|  
|<span data-ttu-id="427fa-420">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-420">DESCRIPTION</span></span>|<span data-ttu-id="427fa-421">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-421">String</span></span>|  
|<span data-ttu-id="427fa-422">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-422">DATE_CREATED</span></span>|<span data-ttu-id="427fa-423">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-423">DateTime</span></span>|  
|<span data-ttu-id="427fa-424">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-424">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-425">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-425">DateTime</span></span>|  
  
### <a name="procedurecolumns"></a><span data-ttu-id="427fa-426">ProcedureColumns</span><span class="sxs-lookup"><span data-stu-id="427fa-426">ProcedureColumns</span></span>  
  
|<span data-ttu-id="427fa-427">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-427">ColumnName</span></span>|<span data-ttu-id="427fa-428">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-428">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-429">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-429">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="427fa-430">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-430">String</span></span>|  
|<span data-ttu-id="427fa-431">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-431">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="427fa-432">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-432">String</span></span>|  
|<span data-ttu-id="427fa-433">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-433">PROCEDURE_NAME</span></span>|<span data-ttu-id="427fa-434">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-434">String</span></span>|  
|<span data-ttu-id="427fa-435">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-435">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-436">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-436">String</span></span>|  
|<span data-ttu-id="427fa-437">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-437">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-438">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-438">Guid</span></span>|  
|<span data-ttu-id="427fa-439">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-439">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-440">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-440">Int64</span></span>|  
|<span data-ttu-id="427fa-441">ROWSET_NUMBER</span><span class="sxs-lookup"><span data-stu-id="427fa-441">ROWSET_NUMBER</span></span>|<span data-ttu-id="427fa-442">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-442">Int64</span></span>|  
|<span data-ttu-id="427fa-443">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-443">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-444">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-444">Int64</span></span>|  
|<span data-ttu-id="427fa-445">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-445">IS_NULLABLE</span></span>|<span data-ttu-id="427fa-446">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-446">Boolean</span></span>|  
|<span data-ttu-id="427fa-447">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-447">DATA_TYPE</span></span>|<span data-ttu-id="427fa-448">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-448">Int32</span></span>|  
|<span data-ttu-id="427fa-449">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-449">TYPE_GUID</span></span>|<span data-ttu-id="427fa-450">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-450">Guid</span></span>|  
|<span data-ttu-id="427fa-451">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-451">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="427fa-452">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-452">Int64</span></span>|  
|<span data-ttu-id="427fa-453">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-453">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="427fa-454">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-454">Int64</span></span>|  
|<span data-ttu-id="427fa-455">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-455">NUMERIC_PRECISION</span></span>|<span data-ttu-id="427fa-456">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-456">Int32</span></span>|  
|<span data-ttu-id="427fa-457">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="427fa-457">NUMERIC_SCALE</span></span>|<span data-ttu-id="427fa-458">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-458">Int16</span></span>|  
|<span data-ttu-id="427fa-459">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-459">DESCRIPTION</span></span>|<span data-ttu-id="427fa-460">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-460">String</span></span>|  
|<span data-ttu-id="427fa-461">OVERLOAD</span><span class="sxs-lookup"><span data-stu-id="427fa-461">OVERLOAD</span></span>|<span data-ttu-id="427fa-462">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-462">Int16</span></span>|  
  
### <a name="views"></a><span data-ttu-id="427fa-463">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="427fa-463">Views</span></span>  
  
|<span data-ttu-id="427fa-464">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-464">ColumnName</span></span>|<span data-ttu-id="427fa-465">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-465">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-466">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-466">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-467">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-467">String</span></span>|  
|<span data-ttu-id="427fa-468">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-468">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-469">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-469">String</span></span>|  
|<span data-ttu-id="427fa-470">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-470">TABLE_NAME</span></span>|<span data-ttu-id="427fa-471">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-471">String</span></span>|  
|<span data-ttu-id="427fa-472">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="427fa-472">VIEW_DEFINITION</span></span>|<span data-ttu-id="427fa-473">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-473">String</span></span>|  
|<span data-ttu-id="427fa-474">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="427fa-474">CHECK_OPTION</span></span>|<span data-ttu-id="427fa-475">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-475">Boolean</span></span>|  
|<span data-ttu-id="427fa-476">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-476">IS_UPDATABLE</span></span>|<span data-ttu-id="427fa-477">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-477">Boolean</span></span>|  
|<span data-ttu-id="427fa-478">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-478">DESCRIPTION</span></span>|<span data-ttu-id="427fa-479">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-479">String</span></span>|  
|<span data-ttu-id="427fa-480">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-480">DATE_CREATED</span></span>|<span data-ttu-id="427fa-481">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-481">DateTime</span></span>|  
|<span data-ttu-id="427fa-482">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-482">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-483">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-483">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="427fa-484">Indexes</span><span class="sxs-lookup"><span data-stu-id="427fa-484">Indexes</span></span>  
  
|<span data-ttu-id="427fa-485">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-485">ColumnName</span></span>|<span data-ttu-id="427fa-486">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-486">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-487">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-487">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-488">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-488">String</span></span>|  
|<span data-ttu-id="427fa-489">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-489">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-490">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-490">String</span></span>|  
|<span data-ttu-id="427fa-491">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-491">TABLE_NAME</span></span>|<span data-ttu-id="427fa-492">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-492">String</span></span>|  
|<span data-ttu-id="427fa-493">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-493">INDEX_CATALOG</span></span>|<span data-ttu-id="427fa-494">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-494">String</span></span>|  
|<span data-ttu-id="427fa-495">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-495">INDEX_SCHEMA</span></span>|<span data-ttu-id="427fa-496">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-496">String</span></span>|  
|<span data-ttu-id="427fa-497">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-497">INDEX_NAME</span></span>|<span data-ttu-id="427fa-498">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-498">String</span></span>|  
|<span data-ttu-id="427fa-499">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="427fa-499">PRIMARY_KEY</span></span>|<span data-ttu-id="427fa-500">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-500">Boolean</span></span>|  
|<span data-ttu-id="427fa-501">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="427fa-501">UNIQUE</span></span>|<span data-ttu-id="427fa-502">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-502">Boolean</span></span>|  
|<span data-ttu-id="427fa-503">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="427fa-503">CLUSTERED</span></span>|<span data-ttu-id="427fa-504">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-504">Boolean</span></span>|  
|<span data-ttu-id="427fa-505">TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-505">TYPE</span></span>|<span data-ttu-id="427fa-506">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-506">Int32</span></span>|  
|<span data-ttu-id="427fa-507">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="427fa-507">FILL_FACTOR</span></span>|<span data-ttu-id="427fa-508">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-508">Int32</span></span>|  
|<span data-ttu-id="427fa-509">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="427fa-509">INITIAL_SIZE</span></span>|<span data-ttu-id="427fa-510">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-510">Int32</span></span>|  
|<span data-ttu-id="427fa-511">NULLS</span><span class="sxs-lookup"><span data-stu-id="427fa-511">NULLS</span></span>|<span data-ttu-id="427fa-512">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-512">Int32</span></span>|  
|<span data-ttu-id="427fa-513">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="427fa-513">SORT_BOOKMARKS</span></span>|<span data-ttu-id="427fa-514">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-514">Boolean</span></span>|  
|<span data-ttu-id="427fa-515">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="427fa-515">AUTO_UPDATE</span></span>|<span data-ttu-id="427fa-516">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-516">Boolean</span></span>|  
|<span data-ttu-id="427fa-517">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-517">NULL_COLLATION</span></span>|<span data-ttu-id="427fa-518">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-518">Int32</span></span>|  
|<span data-ttu-id="427fa-519">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-519">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-520">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-520">Int64</span></span>|  
|<span data-ttu-id="427fa-521">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-521">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-522">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-522">String</span></span>|  
|<span data-ttu-id="427fa-523">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-523">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-524">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-524">Guid</span></span>|  
|<span data-ttu-id="427fa-525">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-525">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-526">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-526">Int64</span></span>|  
|<span data-ttu-id="427fa-527">COLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-527">COLLATION</span></span>|<span data-ttu-id="427fa-528">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-528">Int16</span></span>|  
|<span data-ttu-id="427fa-529">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="427fa-529">CARDINALITY</span></span>|<span data-ttu-id="427fa-530">Decimale</span><span class="sxs-lookup"><span data-stu-id="427fa-530">Decimal</span></span>|  
|<span data-ttu-id="427fa-531">PAGES</span><span class="sxs-lookup"><span data-stu-id="427fa-531">PAGES</span></span>|<span data-ttu-id="427fa-532">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-532">Int32</span></span>|  
|<span data-ttu-id="427fa-533">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="427fa-533">FILTER_CONDITION</span></span>|<span data-ttu-id="427fa-534">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-534">String</span></span>|  
|<span data-ttu-id="427fa-535">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="427fa-535">INTEGRATED</span></span>|<span data-ttu-id="427fa-536">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-536">Boolean</span></span>|  
  
## <a name="microsoft-jet-ole-db-provider"></a><span data-ttu-id="427fa-537">Provider OLE DB per Microsoft Jet</span><span class="sxs-lookup"><span data-stu-id="427fa-537">Microsoft Jet OLE DB Provider</span></span>  
 <span data-ttu-id="427fa-538">Oltre alle raccolte di schemi comuni, il driver OLE DB di Microsoft Jet supporta le raccolte di schemi specifici seguenti:</span><span class="sxs-lookup"><span data-stu-id="427fa-538">The Microsoft Jet OLE DB Driver supports the following specific schema collections in addition to the common schema collections:</span></span>  
  
-   <span data-ttu-id="427fa-539">Tabelle</span><span class="sxs-lookup"><span data-stu-id="427fa-539">Tables</span></span>  
  
-   <span data-ttu-id="427fa-540">Colonne</span><span class="sxs-lookup"><span data-stu-id="427fa-540">Columns</span></span>  
  
-   <span data-ttu-id="427fa-541">Procedure</span><span class="sxs-lookup"><span data-stu-id="427fa-541">Procedures</span></span>  
  
-   <span data-ttu-id="427fa-542">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="427fa-542">Views</span></span>  
  
-   <span data-ttu-id="427fa-543">Indexes</span><span class="sxs-lookup"><span data-stu-id="427fa-543">Indexes</span></span>  
  
### <a name="tables"></a><span data-ttu-id="427fa-544">Tabelle</span><span class="sxs-lookup"><span data-stu-id="427fa-544">Tables</span></span>  
  
|<span data-ttu-id="427fa-545">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-545">ColumnName</span></span>|<span data-ttu-id="427fa-546">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-546">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-547">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-547">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-548">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-548">String</span></span>|  
|<span data-ttu-id="427fa-549">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-549">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-550">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-550">String</span></span>|  
|<span data-ttu-id="427fa-551">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-551">TABLE_NAME</span></span>|<span data-ttu-id="427fa-552">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-552">String</span></span>|  
|<span data-ttu-id="427fa-553">TABLE_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-553">TABLE_TYPE</span></span>|<span data-ttu-id="427fa-554">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-554">String</span></span>|  
|<span data-ttu-id="427fa-555">TABLE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-555">TABLE_GUID</span></span>|<span data-ttu-id="427fa-556">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-556">Guid</span></span>|  
|<span data-ttu-id="427fa-557">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-557">DESCRIPTION</span></span>|<span data-ttu-id="427fa-558">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-558">String</span></span>|  
|<span data-ttu-id="427fa-559">TABLE_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-559">TABLE_PROPID</span></span>|<span data-ttu-id="427fa-560">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-560">Int64</span></span>|  
|<span data-ttu-id="427fa-561">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-561">DATE_CREATED</span></span>|<span data-ttu-id="427fa-562">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-562">DateTime</span></span>|  
|<span data-ttu-id="427fa-563">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-563">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-564">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-564">DateTime</span></span>|  
  
### <a name="columns"></a><span data-ttu-id="427fa-565">Colonne</span><span class="sxs-lookup"><span data-stu-id="427fa-565">Columns</span></span>  
  
|<span data-ttu-id="427fa-566">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-566">ColumnName</span></span>|<span data-ttu-id="427fa-567">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-567">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-568">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-568">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-569">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-569">String</span></span>|  
|<span data-ttu-id="427fa-570">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-570">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-571">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-571">String</span></span>|  
|<span data-ttu-id="427fa-572">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-572">TABLE_NAME</span></span>|<span data-ttu-id="427fa-573">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-573">String</span></span>|  
|<span data-ttu-id="427fa-574">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-574">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-575">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-575">String</span></span>|  
|<span data-ttu-id="427fa-576">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-576">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-577">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-577">Guid</span></span>|  
|<span data-ttu-id="427fa-578">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-578">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-579">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-579">Int64</span></span>|  
|<span data-ttu-id="427fa-580">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-580">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-581">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-581">Int64</span></span>|  
|<span data-ttu-id="427fa-582">COLUMN_HASDEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-582">COLUMN_HASDEFAULT</span></span>|<span data-ttu-id="427fa-583">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-583">Boolean</span></span>|  
|<span data-ttu-id="427fa-584">COLUMN_DEFAULT</span><span class="sxs-lookup"><span data-stu-id="427fa-584">COLUMN_DEFAULT</span></span>|<span data-ttu-id="427fa-585">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-585">String</span></span>|  
|<span data-ttu-id="427fa-586">COLUMN_FLAGS</span><span class="sxs-lookup"><span data-stu-id="427fa-586">COLUMN_FLAGS</span></span>|<span data-ttu-id="427fa-587">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-587">Int64</span></span>|  
|<span data-ttu-id="427fa-588">IS_NULLABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-588">IS_NULLABLE</span></span>|<span data-ttu-id="427fa-589">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-589">Boolean</span></span>|  
|<span data-ttu-id="427fa-590">DATA_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-590">DATA_TYPE</span></span>|<span data-ttu-id="427fa-591">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-591">Int32</span></span>|  
|<span data-ttu-id="427fa-592">TYPE_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-592">TYPE_GUID</span></span>|<span data-ttu-id="427fa-593">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-593">Guid</span></span>|  
|<span data-ttu-id="427fa-594">CHARACTER_MAXIMUM_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-594">CHARACTER_MAXIMUM_LENGTH</span></span>|<span data-ttu-id="427fa-595">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-595">Int64</span></span>|  
|<span data-ttu-id="427fa-596">CHARACTER_OCTET_LENGTH</span><span class="sxs-lookup"><span data-stu-id="427fa-596">CHARACTER_OCTET_LENGTH</span></span>|<span data-ttu-id="427fa-597">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-597">Int64</span></span>|  
|<span data-ttu-id="427fa-598">NUMERIC_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-598">NUMERIC_PRECISION</span></span>|<span data-ttu-id="427fa-599">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-599">Int32</span></span>|  
|<span data-ttu-id="427fa-600">NUMERIC_SCALE</span><span class="sxs-lookup"><span data-stu-id="427fa-600">NUMERIC_SCALE</span></span>|<span data-ttu-id="427fa-601">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-601">Int16</span></span>|  
|<span data-ttu-id="427fa-602">DATETIME_PRECISION</span><span class="sxs-lookup"><span data-stu-id="427fa-602">DATETIME_PRECISION</span></span>|<span data-ttu-id="427fa-603">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-603">Int64</span></span>|  
|<span data-ttu-id="427fa-604">CHARACTER_SET_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-604">CHARACTER_SET_CATALOG</span></span>|<span data-ttu-id="427fa-605">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-605">String</span></span>|  
|<span data-ttu-id="427fa-606">CHARACTER_SET_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-606">CHARACTER_SET_SCHEMA</span></span>|<span data-ttu-id="427fa-607">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-607">String</span></span>|  
|<span data-ttu-id="427fa-608">CHARACTER_SET_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-608">CHARACTER_SET_NAME</span></span>|<span data-ttu-id="427fa-609">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-609">String</span></span>|  
|<span data-ttu-id="427fa-610">COLLATION_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-610">COLLATION_CATALOG</span></span>|<span data-ttu-id="427fa-611">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-611">String</span></span>|  
|<span data-ttu-id="427fa-612">COLLATION_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-612">COLLATION_SCHEMA</span></span>|<span data-ttu-id="427fa-613">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-613">String</span></span>|  
|<span data-ttu-id="427fa-614">COLLATION_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-614">COLLATION_NAME</span></span>|<span data-ttu-id="427fa-615">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-615">String</span></span>|  
|<span data-ttu-id="427fa-616">DOMAIN_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-616">DOMAIN_CATALOG</span></span>|<span data-ttu-id="427fa-617">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-617">String</span></span>|  
|<span data-ttu-id="427fa-618">DOMAIN_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-618">DOMAIN_SCHEMA</span></span>|<span data-ttu-id="427fa-619">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-619">String</span></span>|  
|<span data-ttu-id="427fa-620">DOMAIN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-620">DOMAIN_NAME</span></span>|<span data-ttu-id="427fa-621">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-621">String</span></span>|  
|<span data-ttu-id="427fa-622">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-622">DESCRIPTION</span></span>|<span data-ttu-id="427fa-623">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-623">String</span></span>|  
  
### <a name="procedures"></a><span data-ttu-id="427fa-624">Procedure</span><span class="sxs-lookup"><span data-stu-id="427fa-624">Procedures</span></span>  
  
|<span data-ttu-id="427fa-625">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-625">ColumnName</span></span>|<span data-ttu-id="427fa-626">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-626">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-627">PROCEDURE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-627">PROCEDURE_CATALOG</span></span>|<span data-ttu-id="427fa-628">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-628">String</span></span>|  
|<span data-ttu-id="427fa-629">PROCEDURE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-629">PROCEDURE_SCHEMA</span></span>|<span data-ttu-id="427fa-630">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-630">String</span></span>|  
|<span data-ttu-id="427fa-631">PROCEDURE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-631">PROCEDURE_NAME</span></span>|<span data-ttu-id="427fa-632">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-632">String</span></span>|  
|<span data-ttu-id="427fa-633">PROCEDURE_TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-633">PROCEDURE_TYPE</span></span>|<span data-ttu-id="427fa-634">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-634">Int16</span></span>|  
|<span data-ttu-id="427fa-635">PROCEDURE_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="427fa-635">PROCEDURE_DEFINITION</span></span>|<span data-ttu-id="427fa-636">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-636">String</span></span>|  
|<span data-ttu-id="427fa-637">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-637">DESCRIPTION</span></span>|<span data-ttu-id="427fa-638">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-638">String</span></span>|  
|<span data-ttu-id="427fa-639">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-639">DATE_CREATED</span></span>|<span data-ttu-id="427fa-640">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-640">DateTime</span></span>|  
|<span data-ttu-id="427fa-641">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-641">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-642">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-642">DateTime</span></span>|  
  
### <a name="views"></a><span data-ttu-id="427fa-643">Visualizzazioni</span><span class="sxs-lookup"><span data-stu-id="427fa-643">Views</span></span>  
  
|<span data-ttu-id="427fa-644">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-644">ColumnName</span></span>|<span data-ttu-id="427fa-645">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-645">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-646">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-646">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-647">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-647">String</span></span>|  
|<span data-ttu-id="427fa-648">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-648">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-649">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-649">String</span></span>|  
|<span data-ttu-id="427fa-650">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-650">TABLE_NAME</span></span>|<span data-ttu-id="427fa-651">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-651">String</span></span>|  
|<span data-ttu-id="427fa-652">VIEW_DEFINITION</span><span class="sxs-lookup"><span data-stu-id="427fa-652">VIEW_DEFINITION</span></span>|<span data-ttu-id="427fa-653">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-653">String</span></span>|  
|<span data-ttu-id="427fa-654">CHECK_OPTION</span><span class="sxs-lookup"><span data-stu-id="427fa-654">CHECK_OPTION</span></span>|<span data-ttu-id="427fa-655">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-655">Boolean</span></span>|  
|<span data-ttu-id="427fa-656">IS_UPDATABLE</span><span class="sxs-lookup"><span data-stu-id="427fa-656">IS_UPDATABLE</span></span>|<span data-ttu-id="427fa-657">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-657">Boolean</span></span>|  
|<span data-ttu-id="427fa-658">DESCRIZIONE</span><span class="sxs-lookup"><span data-stu-id="427fa-658">DESCRIPTION</span></span>|<span data-ttu-id="427fa-659">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-659">String</span></span>|  
|<span data-ttu-id="427fa-660">DATE_CREATED</span><span class="sxs-lookup"><span data-stu-id="427fa-660">DATE_CREATED</span></span>|<span data-ttu-id="427fa-661">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-661">DateTime</span></span>|  
|<span data-ttu-id="427fa-662">DATE_MODIFIED</span><span class="sxs-lookup"><span data-stu-id="427fa-662">DATE_MODIFIED</span></span>|<span data-ttu-id="427fa-663">DateTime</span><span class="sxs-lookup"><span data-stu-id="427fa-663">DateTime</span></span>|  
  
### <a name="indexes"></a><span data-ttu-id="427fa-664">Indexes</span><span class="sxs-lookup"><span data-stu-id="427fa-664">Indexes</span></span>  
  
|<span data-ttu-id="427fa-665">Nome colonna</span><span class="sxs-lookup"><span data-stu-id="427fa-665">ColumnName</span></span>|<span data-ttu-id="427fa-666">Tipo di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-666">DataType</span></span>|  
|----------------|--------------|  
|<span data-ttu-id="427fa-667">TABLE_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-667">TABLE_CATALOG</span></span>|<span data-ttu-id="427fa-668">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-668">String</span></span>|  
|<span data-ttu-id="427fa-669">TABLE_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-669">TABLE_SCHEMA</span></span>|<span data-ttu-id="427fa-670">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-670">String</span></span>|  
|<span data-ttu-id="427fa-671">TABLE_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-671">TABLE_NAME</span></span>|<span data-ttu-id="427fa-672">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-672">String</span></span>|  
|<span data-ttu-id="427fa-673">INDEX_CATALOG</span><span class="sxs-lookup"><span data-stu-id="427fa-673">INDEX_CATALOG</span></span>|<span data-ttu-id="427fa-674">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-674">String</span></span>|  
|<span data-ttu-id="427fa-675">INDEX_SCHEMA</span><span class="sxs-lookup"><span data-stu-id="427fa-675">INDEX_SCHEMA</span></span>|<span data-ttu-id="427fa-676">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-676">String</span></span>|  
|<span data-ttu-id="427fa-677">INDEX_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-677">INDEX_NAME</span></span>|<span data-ttu-id="427fa-678">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-678">String</span></span>|  
|<span data-ttu-id="427fa-679">PRIMARY_KEY</span><span class="sxs-lookup"><span data-stu-id="427fa-679">PRIMARY_KEY</span></span>|<span data-ttu-id="427fa-680">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-680">Boolean</span></span>|  
|<span data-ttu-id="427fa-681">UNIQUE</span><span class="sxs-lookup"><span data-stu-id="427fa-681">UNIQUE</span></span>|<span data-ttu-id="427fa-682">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-682">Boolean</span></span>|  
|<span data-ttu-id="427fa-683">CLUSTERED</span><span class="sxs-lookup"><span data-stu-id="427fa-683">CLUSTERED</span></span>|<span data-ttu-id="427fa-684">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-684">Boolean</span></span>|  
|<span data-ttu-id="427fa-685">TYPE</span><span class="sxs-lookup"><span data-stu-id="427fa-685">TYPE</span></span>|<span data-ttu-id="427fa-686">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-686">Int32</span></span>|  
|<span data-ttu-id="427fa-687">FILL_FACTOR</span><span class="sxs-lookup"><span data-stu-id="427fa-687">FILL_FACTOR</span></span>|<span data-ttu-id="427fa-688">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-688">Int32</span></span>|  
|<span data-ttu-id="427fa-689">INITIAL_SIZE</span><span class="sxs-lookup"><span data-stu-id="427fa-689">INITIAL_SIZE</span></span>|<span data-ttu-id="427fa-690">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-690">Int32</span></span>|  
|<span data-ttu-id="427fa-691">NULLS</span><span class="sxs-lookup"><span data-stu-id="427fa-691">NULLS</span></span>|<span data-ttu-id="427fa-692">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-692">Int32</span></span>|  
|<span data-ttu-id="427fa-693">SORT_BOOKMARKS</span><span class="sxs-lookup"><span data-stu-id="427fa-693">SORT_BOOKMARKS</span></span>|<span data-ttu-id="427fa-694">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-694">Boolean</span></span>|  
|<span data-ttu-id="427fa-695">AUTO_UPDATE</span><span class="sxs-lookup"><span data-stu-id="427fa-695">AUTO_UPDATE</span></span>|<span data-ttu-id="427fa-696">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-696">Boolean</span></span>|  
|<span data-ttu-id="427fa-697">NULL_COLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-697">NULL_COLLATION</span></span>|<span data-ttu-id="427fa-698">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-698">Int32</span></span>|  
|<span data-ttu-id="427fa-699">ORDINAL_POSITION</span><span class="sxs-lookup"><span data-stu-id="427fa-699">ORDINAL_POSITION</span></span>|<span data-ttu-id="427fa-700">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-700">Int64</span></span>|  
|<span data-ttu-id="427fa-701">COLUMN_NAME</span><span class="sxs-lookup"><span data-stu-id="427fa-701">COLUMN_NAME</span></span>|<span data-ttu-id="427fa-702">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-702">String</span></span>|  
|<span data-ttu-id="427fa-703">COLUMN_GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-703">COLUMN_GUID</span></span>|<span data-ttu-id="427fa-704">GUID</span><span class="sxs-lookup"><span data-stu-id="427fa-704">Guid</span></span>|  
|<span data-ttu-id="427fa-705">COLUMN_PROPID</span><span class="sxs-lookup"><span data-stu-id="427fa-705">COLUMN_PROPID</span></span>|<span data-ttu-id="427fa-706">Int64</span><span class="sxs-lookup"><span data-stu-id="427fa-706">Int64</span></span>|  
|<span data-ttu-id="427fa-707">COLLATION</span><span class="sxs-lookup"><span data-stu-id="427fa-707">COLLATION</span></span>|<span data-ttu-id="427fa-708">Int16</span><span class="sxs-lookup"><span data-stu-id="427fa-708">Int16</span></span>|  
|<span data-ttu-id="427fa-709">CARDINALITY</span><span class="sxs-lookup"><span data-stu-id="427fa-709">CARDINALITY</span></span>|<span data-ttu-id="427fa-710">Decimale</span><span class="sxs-lookup"><span data-stu-id="427fa-710">Decimal</span></span>|  
|<span data-ttu-id="427fa-711">PAGES</span><span class="sxs-lookup"><span data-stu-id="427fa-711">PAGES</span></span>|<span data-ttu-id="427fa-712">Int32</span><span class="sxs-lookup"><span data-stu-id="427fa-712">Int32</span></span>|  
|<span data-ttu-id="427fa-713">FILTER_CONDITION</span><span class="sxs-lookup"><span data-stu-id="427fa-713">FILTER_CONDITION</span></span>|<span data-ttu-id="427fa-714">Stringa</span><span class="sxs-lookup"><span data-stu-id="427fa-714">String</span></span>|  
|<span data-ttu-id="427fa-715">INTEGRATED</span><span class="sxs-lookup"><span data-stu-id="427fa-715">INTEGRATED</span></span>|<span data-ttu-id="427fa-716">Booleano</span><span class="sxs-lookup"><span data-stu-id="427fa-716">Boolean</span></span>|  
  
## <a name="see-also"></a><span data-ttu-id="427fa-717">Vedere anche</span><span class="sxs-lookup"><span data-stu-id="427fa-717">See also</span></span>

- [<span data-ttu-id="427fa-718">Provider gestiti ADO.NET e Centro per sviluppatori di set di dati</span><span class="sxs-lookup"><span data-stu-id="427fa-718">ADO.NET Managed Providers and DataSet Developer Center</span></span>](https://go.microsoft.com/fwlink/?LinkId=217917)
