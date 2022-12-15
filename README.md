### [Hi there!](https://twitter.com/alexdaubois/) 👋

```php
<?php

namespace App\Developer;

#[AsHuman]
final class AlexDaubois extends AbstractSymfonyLeadSensioLabsDeveloper implements DeveloperInterface
{
    use TwigTrait;
    use OpsTrait;

    public const FIRST_NAME = 'Alexandre';
    public const LAST_NAME = 'Daubois';
    
    public function __construct(
        private \DateTimeImmutable $birthDate = new \DateTimeImmutable('1996-01-07T05:30:00+0200'),
        private string $currentCompany = 'Wanadev',
        private string $currentCity = 'Lyon, France'
    ) {
    }
    
    public function getBlog(): ?SocialAccountInterface
    {
        return new MediumPage('https://alex-daubois.medium.com/');
    }
    
    public function getTwitter(): ?SocialAccountInterface
    {
        return new TwitterAccount('https://twitter.com/alexdaubois');
    }
    
    public function isCertified(): bool
    {
        return true;
    }
    
    public function getCertificationLabel(): ?string
    {
        return $this->isCertified() ? 'Symfony 6 Certified Developer (Expert)' : null;
    }
}
```
