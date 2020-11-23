# Securing The Recipe Vault Web Application

**Content**

**This Project consist of four Parts; Design, Detecting, Recommend, and Implement & Monitoring**


* [Design The DevSecOps Pipeline](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/DevSecOpsPipeline.png)

* [Detecting The Security Loopholes](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E1T4.txt)

* [Recommending Security Best Practices](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E2T2.txt)

* [Security Compliance with AWS Config](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E2T2_config.png)

* [Detecting Bruteforce Attack with AWS GaurdDuty]()


<br><br/>
## Design The DevSecOps Pipeline

The Security Design uses a DevSecOps approach other than the usual method of scanning codes, Security scanning begins from IDLE environment and warns the Software Engineer of potential vulnerability at the time of writing the code.

![](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/DevSecOpsPipeline.png)
[Fig 1.1: DevSecOps Pipeline](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/DevSecOpsPipeline.png)
<br><br/>


## Detecting The Security Loopholes

After observing the Infrastructure, below are the findings

| 1. Absence of Least Privilege caused Excessive Permissions on S3 Bucket |
| ------------------------------------------------------------ |
| The IAM role assigned to S3 Bucket give full access to all resources. |
| The is not the best practice as it does not followed the principle of Least Privelege. |
|                                                              |
| 2. Security Group IP Protocol & Network CIDR Block           |
| The Web Server allows all type of connections from all Protocols and IP addresses. |
| The Security Group does not addresses the connection from only secure trusted Groups of Ip addresses and Protocols. |

<details class="details-reset details-overlay details-overlay-dark" id="jumpto-line-details-dialog" style="box-sizing: border-box; display: block;"><summary data-hotkey="l" aria-label="Jump to line" role="button" style="box-sizing: border-box; display: list-item; cursor: pointer; list-style: none;"></summary></details>
Table 1.1: Detecting Secuirty loopholes
<br><br/>

## Recommending Security Best Practices

**My recommendations**

| 1. All Security Groups should deny all inbound traffic and should only accept traffic assigned instances. |
| ------------------------------------------------------------ |
| Removed all open ports (-1) exposed to Internet except the required (80, 22). |
| Reduced the CIDR Block to only required addresses (10.2.12.0/24) in the place of 0.0.0.0/0. |
| 2. S3 Bucket (Free_Recipe) "Public Access Write" should be removed and Server-Side Encryption should be enabled with AWS-KMS. |
| Use the ACL to specify and streamline who has access to Read the Bucket Objects. |
|                                                              |
| 3. S3 BUcket (Secret_Recipe) Public Access Read/Write should be removed, Enable Server-Side Encryption and Versioning. |
|                                                              |
| 4. Update EC2 Instance, (Os) Vulnerability of root privilege escalation, XML injection and other security patches should be fixed with update. |
|                                                              |
| 5. Set Password Policy, assigned Password Complexity/Restrictions to reduce the use of simple password and reused of previous password hat can allow an unauthorized personnel to easily gain access. |

<details class="details-reset details-overlay details-overlay-dark" id="jumpto-line-details-dialog" style="box-sizing: border-box; display: block;"><summary data-hotkey="l" aria-label="Jump to line" role="button" style="box-sizing: border-box; display: list-item; cursor: pointer; list-style: none;"></summary></details>
Table 1.2: Recommending Security Best Practices
<br><br/>

## Security Compliance with AWS Config

 The initial configuration before applying recommendation and best practices.

![](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E2T2_config.png)
[Fig 1.2: Security Compliance with AWS Config](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E2T2_config.png)
<br><br/>

## Detecting Bruteforce Attack with GuardDuty

![](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E3T1_guardduty.png)
[Fig 1.3: Detecting Bruteforce Attack with Gaurdduty](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E3T1_guardduty.png)
<br><br/>

## GuardDuty Findings - After implementing the recommendations following the best practices

AWS Config rules and the compliance.

![](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E4T3_config.png)
[Fig 1.4: Guardduty Findings](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application/blob/master/E4T3_config.png)
<br><br/>

### [Summary](https://github.com/eedygreen/Securing-the-Recipe-Vault-Web-Application)

The project was based on infrastructure security from development environment to production using the DevSecOps approach and monitoring the infrastructure security compliance on AWS platform.



<sup>Securing The Recipe Vault Web Application</sup>
