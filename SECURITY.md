# Security Policy

> [!NOTE]
>
> EU Cyber Resilience Act (CRA) stewardship: This project is supported under the
> Linux Foundation CRA stewardship framework, as described at
> https://www.linuxfoundation.org/security. Security vulnerabilities should be
> reported through the mechanisms described below, which we will coordinate with
> our CRA steward. For actively exploited vulnerabilities and severe incidents
> that may require CRA escalation, please use the project’s emergency security
> reporting mechanisms as appropriate.

## Reporting a Vulnerability

> [!NOTE]
>
> Make sure to send your report to a code repository such as <https://github.com/containerd/containerd>.
>
> Do not send any report to <https://github.com/containerd/.project>.

To report a containerd vulnerability:

* Navigate to the security tab on the repository
![Github Security Tab](./img/Security-Tab.png)

* Click on `Advisories`
![Github Advisories tab](./img/Advisories.png)

* Click on `Report a vulnerability`
![Report a vulnerability](./img/Report-A-Vulnerability.png)

The reporter(s) can expect a response within 24 hours acknowledging
the issue was received. If a response is not received within 24 hours, please
reach out to any committer directly to confirm receipt of the issue.

## Review Process

Once a committer has confirmed the relevance of the report, a draft security
advisory will be created on Github. The draft advisory will be used to discuss
the issue with people including committers, the reporter(s), and containerd's security advisors.
If the reporter(s) wishes to participate in this discussion, then provide
reporter Github username(s) to be invited to the discussion. If the reporter(s)
does not wish to participate directly in the discussion, then the reporter(s)
can request to be updated regularly via email.

If the vulnerability is accepted, a timeline for developing a patch, public
disclosure, and patch release will be determined. If there is an embargo period
on public disclosure before the patch release, an announcment will be sent to
the security announce mailing list(`containerd-security-announce@lists.cncf.io`)
announcing the scope of the vulnerability, the date of availability of the
patch release, and the date of public disclosure. The reporter(s) are expected
to participate in the discussion of the timeline and abide by agreed upon dates
for public disclosure.

Prior to the public disclosure, the vulnerability may be shared with:
- Owners of the `@containerd` organization, including CNCF staff
- Committers
- Security Advisors
- Reporter(s)
- Reporter(s) of identical or very similar vulnerabilities
- Additional contributors or experts who can provide context, at the discretion
  of the Committers
- Members of the containerd disclosure distribution list

## Supported Versions

See the [containerd releases page](https://github.com/containerd/containerd/blob/master/RELEASES.md#support-horizon)
for information on supported versions of containerd. Any `Extended` or `Active`
release branch may receive security updates. For any security issues discovered
on older versions, non-core packages, or dependencies, please inform committers
using the same security mailing list as for reporting vulnerabilities.

## Coordinated disclosure

The containerd project operates a coordinated disclosure distribution list with
the goal of enabling downstream distributors of containerd to produce patched
builds and guidance for their end users with minimal delay after the containerd
maintainers disclose vulnerabilities publicly.

### Joining the security announce mailing list

Any organization or individual who directly uses containerd and non-core
packages in production or in a security critical application is eligible to join
the security announce mailing list. Indirect users who use containerd through a
vendor are not expected to join, but should request their vendor join. To join
the mailing list, the individual or organization must be sponsored by either a
containerd committer or security advisor as well as have a record of properly
handling non-public security information.
Sponsorship should not be requested via public channels since membership of the
security announce list is not public.

### Embargo policy

The information members receive from the distribution list must not be made
public, shared, nor even hinted at anywhere beyond the need-to-know within your
specific team except with the list's explicit approval. This holds true until
the public disclosure date/time that was agreed upon by the list. Members of the
list and others may not use the information for anything other than getting the
issue fixed for your respective distribution's users.

Before any information from the list is shared with respective members of your
team required to fix said issue, they must agree to the same terms and only find
out information on a need-to-know basis.

List members may ask for approval to share information and builds with each
other ahead of public disclosure. Members who use containerd builds from another
member OS distributor may wish to receive builds ahead of public disclosure for
testing and qualification. Members who ask for approval should include the
following information in their request:

* the specific list of members who are included in the request
* the specific class of vulnerabilities the members collaborate for
* what information (e.g. vulnerability details, software artifacts) will be
  exchanged and how it will be protected (access controls)
* the purposes for which the information exchanged will be used
* explicit acknowledgement by all included members that the rest of the embargo
  policy remains in force

In the unfortunate event you share the information beyond what is allowed by
this policy, you must urgently inform the containerd maintainers of exactly what
information leaked and to whom. Evidence of public exploits should be reported
back to the list for coordination and discussion of a new public disclosure
date/time; unilateral or uncoordinated publication of embargoed information is
not permitted. A retrospective will take place after the leak so we can assess
how to not make the same mistake in the future.

If you leak information and break the policy outlined here, you may be removed
from the list.

### Member responsibilities

This is a team effort. As a member of the list you are expected to review and/or
test the proposed patches and to point out potential issues with them (such as
incomplete fixes for the originally reported issues, additional issues you might
notice, and newly introduced bugs). Members should inform the list of the work
done even if no issues were encountered.

### Vulnerabilities included

The containerd maintainers, at their sole discretion, will decide which
vulnerabilities are sent to the coordinated disclosure distribution list.
Criteria for determining whether an embargo should be in force or how long the
embargo period lasts include but are not limited to: severity, ease of
exploitation, and evidence of public exploitation. The containerd maintainers do
not typically use the list for low- or moderate-severity vulnerabilities.