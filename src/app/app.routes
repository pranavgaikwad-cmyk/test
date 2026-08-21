import { verificationGuard } from './core/guards/verification.guard';

export const routes: any = [
  { path: '', redirectTo: 'login', pathMatch: 'full' },
  {
    path: 'login',
    loadComponent: () =>
      import('./features/auth/login/login.component').then((item: any) => item.LoginComponent),
  },
  {
    path: 'complete-setup',
    loadComponent: () => import('./features/auth/complete-setup/complete-setup.component').then((item: any) => item.CompleteSetupComponent),
  },
  {
    path: 'payment-packages',
    loadComponent: () => import('./features/payment-packages/payment-packages.component').then((item: any) => item.PaymentPackagesComponent),
  },
  {
    path: 'app',
    canActivate: [verificationGuard],
    loadComponent: () => import('./layout/app-shell/app-shell.component').then((item: any) => item.AppShellComponent),
    children: [
      { path: '', redirectTo: 'dashboard', pathMatch: 'full' },
      { path: 'dashboard', loadComponent: () => import('./features/dashboard/dashboard.component').then((item: any) => item.DashboardComponent) },
      { path: 'skill-passport', loadComponent: () => import('./features/skill-passport/skill-passport.component').then((item: any) => item.SkillPassportComponent) },
      { path: 'jobs', loadComponent: () => import('./features/jobs/jobs.component').then((item: any) => item.JobsComponent) },
      { path: 'assess', loadComponent: () => import('./features/assessments/assessments.component').then((item: any) => item.AssessmentsComponent) },
      { path: 'assess/:attemptId', loadComponent: () => import('./features/assessments/assessments.component').then((item: any) => item.AssessmentsComponent) },
      { path: 'level-up', loadComponent: () => import('./features/level-up/level-up.component').then((item: any) => item.LevelUpComponent) },
      { path: 'profile', loadComponent: () => import('./features/profile/profile.component').then((item: any) => item.ProfileComponent) },
      { path: 'payment-packages', loadComponent: () => import('./features/payment-packages/payment-packages.component').then((item: any) => item.PaymentPackagesComponent) },
    ],
  },
  { path: 'dashboard', redirectTo: 'app/dashboard', pathMatch: 'full' },
  { path: '**', redirectTo: 'login' },
];
