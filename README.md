# LinkedIn Certification Checker

**Yes or no: does this LinkedIn profile have the certification you named? $1 per 1,000 profiles.**

Recruiters filtering a list. One profile is one row and one charge. `hasCertification` is true or false. A miss is still a successful row.

## Who is this for?

Recruiting teams screening for one certificate, such as AWS Certified Solutions Architect, PMP, or a Six Sigma belt. Use Certifications and Patents when you need every certificate exported.

## How to run it

```json
{
  "certification": "AWS Certified Solutions Architect",
  "aliases": ["AWS SAA", "Solutions Architect"],
  "urls": ["https://www.linkedin.com/in/example"]
}
```

A profile matches if the certification name, or any alias, appears on a certification. Short names such as PMP match as a whole word. Paste a CSV with a `url` column, or upload a CSV file.

## What does a row look like?

```json
{
  "inputUrl": "https://www.linkedin.com/in/example",
  "fullName": "Example Person",
  "headline": "Cloud Engineer",
  "requiredCertification": "AWS Certified Solutions Architect",
  "hasCertification": true,
  "matchedTitle": "AWS Certified Solutions Architect – Associate",
  "matchedIssuer": "Amazon Web Services",
  "certificationCount": 4,
  "success": true
}
```

Filter the dataset to `hasCertification` = true and send that list on.

## FAQ

### Is a "no" a failed run?

No. `success` is true and `hasCertification` is false. You are charged once either way, because the profile was checked.

### Why not use Certifications and Patents?

That Actor is also $1 per 1,000 and returns every certificate, patent, course, and publication. Use it when you want the export. Use this Actor when the only question is whether they have the one you require.

### Why not use Profile Details?

Profile Details is $1.80 per 1,000 and returns the job, about, education, and activity as well. This check is the filter.

### Does a long list keep going?

Yes. Up to 50,000 URLs. Ten profiles run at a time, and you can raise that to 40. A list over 200 resumes on the next run. Change the certification name with the same `resumeId` and finished profiles are checked again, because the saved progress includes the name you asked for.

## Related Actors

Certifications and Patents for the full credential export. Work Experience and Education for the other recruiting fields. Profile Details for the whole page.

## Where to run it

Run the published Actor on Apify, or start from [mawsool.tech](https://mawsool.tech). This repository does not include the lookup address.
